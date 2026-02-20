# BI Clicker Dashboard

An interactive R Shiny dashboard for exploring iClicker and quiz data from a Cornell Business Intelligence course (2016–2018, 123 students).

## Demo

[![Demo Video](https://img.youtube.com/vi/QXn3rLqMKp0/0.jpg)](https://youtu.be/QXn3rLqMKp0)
---

## Overview

Two dashboards, two audiences:

- **Instructor View** — Class-wide attendance trends, quiz score distributions, grad vs. undergrad performance, clicker engagement, and a skill background scatter plot across 6 panels.
- **Student View** — A fully reactive, per-student view of quiz trajectory vs. class average, clicker engagement, sentiment over time, and skill background vs. class median.

## Tech Stack

R · tidyverse · ggplot2 · Shiny · shinydashboard · scales

## Getting Started

1. **Install dependencies**
   ```r
   install.packages(c("shiny", "shinydashboard", "tidyverse", "scales"))
   ```

2. **Load your data** — The app expects two data frames:
   - `quiz` — one row per student per session (attendance, clicker, quiz scores)
   - `experience` — one row per student (skill survey responses, program type)

3. **Run the app**
   ```r
   shiny::runApp("app.R")
   ```
   Or run the final chunk interactively in RStudio — the dashboard opens in the Viewer pane.

## Key Design Decisions

- Clicker completion rate is excluded (not zeroed) for sessions with no questions asked.
- Student selector is fully reactive — all plots update instantly on student change.
- `req()` guards prevent errors on initial load before the selector populates.

## Author

Aaradhyaa Gyawali 
