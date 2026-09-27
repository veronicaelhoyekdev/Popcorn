# Popcorn — Android Client

Native Android client for a movie discovery and review platform, built with **Java** and connected to a dedicated REST backend through **Retrofit**.

## Overview

Popcorn is a mobile application for discovering movies, exploring detailed movie information, managing personal watchlists, tracking watched movies, and creating reviews.

The Android client combines external movie content with application-specific user data exposed through a REST backend. Networking is handled through Retrofit and OkHttp, with Gson used for JSON serialization and deserialization.

## Features

### Movie Discovery

- Browse popular movies
- Browse movies currently playing
- Discover upcoming releases
- Search for movies
- View detailed movie information
- Explore similar movies
- View cast and crew information

### User Features

- Account registration and sign-in
- Account verification
- Personal watchlist
- Watched movie tracking
- Movie reviews
- Review creation and editing
- User-specific movie data

## Tech Stack

| Area | Technology |
| --- | --- |
| Platform | Android |
| Language | Java |
| UI | Android XML |
| API Client | Retrofit |
| HTTP Client | OkHttp |
| Serialization | Gson |
| Lists | RecyclerView |
| Image Loading | Picasso |
| Build | Gradle |
| Backend Communication | REST API |

## Application Structure

The client is organized by application responsibility:

```text
app/src/main/
├── java/com/example/popcorn/
│   ├── Activities/       # Screens and navigation
│   ├── Adapters/         # RecyclerView presentation
│   ├── DTOs/             # API request/response models
│   ├── Models/           # Application domain models
│   └── Networking/       # REST communication and data retrieval
│
├── res/
│   ├── drawable/         # Visual assets
│   ├── layout/           # Screen layouts
│   ├── menu/             # Application menus
│   └── values/           # Strings, themes and resources
│
└── AndroidManifest.xml
```

## Client Architecture

```text
Android UI
    │
    ▼
Activities
    │
    ├──────────────► RecyclerView Adapters
    │
    ▼
Networking Layer
    │
    ├── Retrofit
    ├── OkHttp
    └── Gson
    │
    ▼
REST Backend
```

Activities coordinate user interactions and application navigation, while dedicated networking components communicate with the backend and transform API responses into application models.

## REST API Integration

Retrofit provides the main interface between the Android application and the Popcorn backend.

The networking layer supports operations related to:

- Authentication
- Movie data
- Reviews
- Watchlists
- Watched movies
- User-specific content

OkHttp is used as the underlying HTTP client, including a local HTTP response cache.

## Movie Experience

Movie content is presented across dedicated screens for discovery, search, and detailed exploration.

Movie detail views combine general movie information with related data such as cast, crew, similar movies, reviews, and user-specific state.

RecyclerView-based interfaces are used throughout the application to efficiently display dynamic collections of movies and related content.

## Reviews

Authenticated users can interact with the review system directly from the Android application.

Dedicated screens support:

- Viewing reviews
- Creating a review
- Editing an existing review

Review operations communicate with the backend through the application's REST networking layer.

## Watchlist & Watched Movies

The application maintains separate user-specific collections for:

- Movies saved to a watchlist
- Movies marked as watched

Dedicated networking tasks retrieve and synchronize these collections with the backend.

## Getting Started

### Prerequisites

- Android Studio
- Android SDK
- Java Development Kit compatible with the project's Gradle configuration
- Access to a compatible Popcorn backend

### Installation

Clone the repository:

```bash
git clone https://github.com/veronica-el-hoyek/Popcorn---Frontend.git
```

Open the project in Android Studio and allow Gradle to synchronize the required dependencies.

Run the application using an Android emulator or physical Android device.

## Backend Configuration

The REST backend URL is configured in the application's Retrofit client.

```text
https://popcorn-4gmf.onrender.com/
```

To connect the application to another compatible backend instance, update the base URL in the networking configuration.

## Project Context

Mobile software engineering project focused on native Android development, REST API integration, client-server architecture, authentication flows, asynchronous data handling, and user-specific application state.

This repository contains the **Android client** of the Popcorn application.

## Author

**Veronica El Hoyek**  
Software & AI Engineer

Portfolio: https://veronica-el-hoyek.vercel.app/  
GitHub: https://github.com/veronica-el-hoyek