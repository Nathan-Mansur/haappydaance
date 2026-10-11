# Haappy Daance Booking Calendar

A custom class booking calendar for a dance studio.
It embeds in the studio's Squarespace site and pulls live class data from Acuity Scheduling.

**Live site:** https://www.haappydaance.com/




## What it does

- Shows upcoming classes on an interactive calendar (month, week, and list views)
- Color-codes events by audience (Kids / Adults)
- Card-based class list with details parsed from Acuity (level, instructor, age range, etc.)
- Archives past classes so the live calendar stays fast and clean
- Responsive sidebar for filtering and class details
- Booking handoff straight into Acuity's scheduling flow

## Architecture

    Squarespace site  -->  FullCalendar frontend
                                  |
                                  v
                      Vercel serverless API
                       /                  \
              Acuity Scheduling API    Vercel Blob
              (classes, availability)  (past-class archive)

## Tech stack

| Layer | Tools |
|---|---|
| Website | Squarespace |
| Scheduling | Acuity Scheduling API |
| Frontend | FullCalendar, JavaScript, CSS |
| Backend | Vercel serverless functions |
| Storage | Vercel Blob |

## Interesting problems solved

- **Squarespace compatibility:** fixing z-index stacking and font inheritance so the
  embedded calendar renders correctly inside Squarespace's CSS.
- **Metadata parsing:** turning Acuity's free-form class descriptions into structured
  fields for the card layout.
- **Archiving:** moving past classes into Vercel Blob so the API stays fast as the
  schedule grows.

## Screenshots

| Calendar | Class list | Sidebar |
|---|---|---|
| <img width="1451" height="895" alt="image" src="https://github.com/user-attachments/assets/d75e445d-605c-4b83-9f0b-6e7c76693ce5" />
 | ![](screenshots/list.png) | ![](screenshots/sidebar.png) |

## About this repo

The production code is kept private because it connects to the studio's live
accounts. This repo is a showcase of the project's design and features.

## Contact

Built by [Nathan Mansur](https://nathanmansur.com).
