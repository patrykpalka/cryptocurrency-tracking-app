# Cryptocurrency Tracking App – Full Stack Project

A complete full-stack application for tracking cryptocurrency prices, built with a **Spring Boot backend** and an **Android mobile frontend**. The app fetches real-time and historical data using the CoinGecko API and provides a simple, mobile-friendly UI for end users.

## Table of Contents

* [Overview](#overview)
* [Monorepo Structure](#monorepo-structure)
* [Features](#features)
* [Tech Stack](#tech-stack)
* [Installation & Running](#installation--running)
* [Modules](#modules)
* [Author](#author)

## Overview

This project consists of two main components:

* **Backend** – built with Spring Boot, provides a REST API that connects to the external CoinGecko API and serves cryptocurrency data.
* **Android App** – consumes the backend API to display live market data and historical charts on Android devices.

This repository uses a **multi-module structure** with independent README files for each component.

## Monorepo Structure

```
cryptocurrency-tracking-app/
│
├── backend/            → Spring Boot backend
│   └── README.md
│
├── android-client/     → Android application in Java
│   └── README.md
│
└── README.md           → (you are here)
```

## Features

- Fetch current prices for selected cryptocurrencies (via backend)
- Display list of supported coins
- Historical price data with date range selection
- Market data: market cap, volume, circulating supply
- Currency validation using @ValidCurrency annotation
- Input validation and centralized exception handling
- Caching of supported coins list (auto-refresh every 12h)
- REST API with clear separation via DTOs
- Error handling for network/API issues on Android
- Modern Material UI with clear, responsive layout
- Android-specific features:
  - Retrofit 2 for network calls
  - Gson for JSON parsing
  - Live data display in recycler views
- Unit and UI testing:
  - Backend: JUnit 5, Mockito
  - Android: JUnit, Espresso

## Tech Stack

### Backend

- Java 17
- Spring Boot:
  - Spring WebFlux (non-blocking reactive API)
  - Spring Validation (input validation)
  - Spring Cache (currency list caching)
- Custom annotations and exception handling
- SLF4J (logging)
- Maven (build tool)
- JUnit 5, Mockito (unit testing)
- CoinGecko API (external data source)

### Frontend (Android)

- Java 17
- Android SDK 30+
- Retrofit 2 (HTTP client)
- Gson (JSON parsing)
- Material Components for UI
- RecyclerView, ViewBinding
- Gradle (build tool)
- JUnit, Espresso (unit & UI testing)

## Installation & Running

### Prerequisites

* JDK 17+
* Android Studio (Arctic Fox or newer)
* Internet connection

### Running the Backend

```bash
cd backend
mvn clean spring-boot:run
```

### Running the Android App

1. Start backend (`http://10.0.2.2:8080/` for emulator).
2. Open `android-client/` in Android Studio.
3. Build and run on an emulator or physical device.

## Modules

Each component has its own README with more details:

* [`/backend`](https://github.com/patrykpalka/cryptocurrency-tracking-backend/blob/master/README.md) – Spring Boot API with data validation and caching
* [`/android-client`](https://github.com/patrykpalka/crypto-tracking-android-app/blob/master/README.md) – Android UI with network integration

## Author

[Patryk Palka - GitHub](https://github.com/patrykpalka)

Feel free to contribute, fork, or reach out with feedback!