# Daegu Apartment — Property Search, Recommendation & Price Forecasting

**Daegu Apartment** (대구아파트) is a **2021 team-developed real-estate Android app** designed to help users discover and compare apartments in Daegu, South Korea. The original team's concept combined apartment search with personalized recommendations and forecasts of apartment prices for the following **three months**.

The original project used **Java, Python, PHP, and MySQL** across the application and supporting work. **This repository primarily contains the Java Android client**; the full Python prediction/recommendation implementation, PHP server, MySQL database schema, and crawling pipeline are not available here. Consequently, those components and the historical accuracy of the forecasts cannot be independently reproduced from this repository.

## Project capabilities

| Capability | Scope |
| --- | --- |
| Apartment search | Filters for apartment name, district, price, floor area, and nearby facilities |
| Listings and details | Apartment lists, detailed information, and map-based browsing |
| Recommendations | Apartment recommendation and TOP ranking screens |
| Comparison | Saved properties and chart-based comparisons |
| Price forecasting | Historical team feature intended to predict three months of apartment prices; the underlying model implementation is not in this repository |
| Accounts | Sign-in, registration, and recovery screens |

The code shows Android-side implementations of the search, listing, details, ranking, map, favorites, and comparison screens. Live service functionality is not currently verified.

## My contributions

I worked on the following parts of this team project:

- **Database design and implementation:** designed and built the project's database.
- **Recommendation algorithm:** implemented a matrix factorization (MF) recommendation algorithm.
- **Data collection:** implemented web crawling for property data.
- **Android app development:** developed the apartment search, listing, recommendation, property detail, and TOP ranking features.

These contributions are described from the original project record and my recollection. The repository's single initial upload commit was authored as **노강은 (Kangeun Noh)** on July 12, 2021, but a bulk upload does not by itself prove individual authorship of each file. The database, crawler, and recommendation algorithm source are not included here, and their behavior is not represented as independently verified.

## Technology

- **Android:** Java, Android SDK 29, Android Gradle Plugin 4.1.1, Gradle 6.5
- **Client networking:** Retrofit, OkHttp, Gson, Volley
- **UI and mapping:** AndroidX, RecyclerView, Naver Maps SDK, MPAndroidChart
- **Original supporting stack (not included here):** Python, PHP, MySQL

## Repository structure

```text
app/src/main/java/org/techtown/apt_1025/
  KActivity/       Apartment search, map, details, rankings
  KNetwork/        Retrofit client, routes and response models
  Login/           Registration and account screens
  MainScreen/      Navigation and main application interface
  MyApart/         Saved apartments, comparison, prediction UI
app/src/main/res/  Android layouts and assets
```

Selected files: `KActivity/SearchApartActivity.java`, `KActivity/DetailInfoActivity.java`, `KActivity/RankingActivity.java`, `MyApart/CompareActivity.java`, and `MyApart/PredictActivity.java`.

## Reproduction and maintenance status

This is a **historical educational team project**, not a maintained commercial application. The repository is not currently self-contained or reproducibly runnable:

- The Android build uses old versions and references retired JCenter/Bintray-hosted dependencies.
- The original HTTP backend, Python analysis/forecast code, PHP services, MySQL schema, and crawling jobs are not included.
- Map access and service endpoints would need current, authorized configuration.
- The app has not been rebuilt or tested against a modern Android toolchain.
- No prediction-error metrics, recommendation-quality evaluation, benchmark, or modern automated integration tests are provided.

Reviving the app would require rebuilding the backend contract, migrating Android dependencies, adding a testable recommendation/forecasting pipeline, and verifying each feature on a current device.

## Security note

The original mobile source contained an embedded SMTP account and password. Those values have been removed from the current email utility, leaving legacy email delivery unconfigured. **Old Git history still contains them**, so the account owner must change/revoke that credential. Email verification should be performed server-side, never by distributing SMTP credentials in an Android app.

The legacy client also permits cleartext HTTP and points to a fixed backend host. This transport and credential design must be replaced before any real deployment.

## Attribution

Developed as a team project in 2021. The personal contributions listed above are limited to the work stated in the original project description; the application as a whole is **not claimed as sole-authored**.
