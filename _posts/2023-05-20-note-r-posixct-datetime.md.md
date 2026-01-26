---
title: "[Note] Handling Date-Time Data in R with as.POSIXct()"
date: 2026-01-26
categories: [Note]
---

## Introduction

Time-series data are common in ecological experiments, such as hourly temperature records or interannual biomass variation.

In base R, time data are mainly represented in three formats:

- Date: number of days since 1970-01-01  
- POSIXct: number of seconds since 1970-01-01 (UTC-based)  
- POSIXlt: list-based structure storing date, time, and timezone  

Time objects are usually created by converting character strings using:

- as.Date()  
- as.POSIXct()  
- as.POSIXlt()  
- strptime()  

The lubridate package also provides convenient tools.

This note focuses on the basic usage of as.POSIXct().

---

## Basic syntax

    as.POSIXct(x, tz = "", format = "", origin = "", ...)

Arguments:

- x: object to convert (usually a character string)  
- tz: timezone (default is system timezone)  
- format: string format specification  
- origin: starting date for numeric time values  

---

## Example 1: Simple conversion

    t1 = '2022-02-22 22:22:22'
    class(t1)

    t1 = as.POSIXct(t1)
    class(t1)

---

## Example 2: Specify format

    t2 = '2022/02/22T22:22:22'
    t2 = as.POSIXct(t2, format = '%Y/%m/%dT%H:%M:%S')
    t2

Common format symbols:

- %y  two-digit year  
- %Y  four-digit year  
- %m  month  
- %d  day  
- %b  abbreviated month  
- %B  full month name  
- %a  abbreviated weekday  
- %A  full weekday  

---

## Example 3: Timezones

    library(lubridate)

    t3 <- as.POSIXct('2022-02-23 23:23:23', tz = 'UTC')
    t3

    t4 <- as.POSIXct('2022-02-24 01:00:00', tz = 'America/New_York')
    t4

    with_tz(t4, 'GMT')

---

## Example 4: UNIX time origin

    t5 = 1645564942
    as.POSIXct(t5, origin = '1970-01-01')
    as.POSIXct(t5, origin = '1980-01-01')

---

## Plotting date-time data with ggplot2

    library(ggplot2)
    library(scales)

    set.seed(2022)

    a = 4
    b = 7
    amp = 2
    n = 7 * 24 * 4

    t = seq(0, 2*pi, , n)
    h.norm = rnorm(n)

    h.temp = a*sin(b*t + 1.5*pi) + h.norm*amp + 25

    dt = seq.POSIXt(
      as.POSIXct("2022-02-01 00:00:00"),
      as.POSIXct("2022-02-07 23:45:00"),
      tz = "Europe/Berlin",
      by = "15 min"
    )

    df.temp = data.frame(datetime = dt, temptr = h.temp)

    ggplot(df.temp, aes(x = datetime, y = temptr)) +
      geom_line(size = 1.5, col = "red") +
      xlab("Measuring time") +
      ylab("Measured temperature (°C)") +
      ylim(15, 35) +
      scale_x_datetime(
        labels = date_format("%m/%d/%y"),
        breaks = date_breaks("1 day")
      ) +
      ggtitle("Air temperature variation") +
      theme(
        plot.title = element_text(size = 20, face = "bold", hjust = 0.5),
        axis.title = element_text(size = 15, face = "bold"),
        axis.text = element_text(size = 12, face = "bold")
      )

---

## Further reading

- lubridate package documentation and cheatsheets

End of note.
