# Changelog

All notable changes to this project are documented in this file.

## [v1.0.0] - 2026-04-18

### Summary
Initial publication of the CarQuest API as a clean, portfolio-ready Spring Boot REST project.

### Highlights

- Added standardized `README.md` with API overview, run steps, and endpoint summary.
- Added `CHANGELOG.md` for future version tracking.
- Cleaned IDE files, temp files, and build artifacts before publishing.
- Preserved the original car CRUD and JWT authentication workflow.

### Notes

This version establishes the project as a compact learning showcase for JWT-secured CRUD APIs with Spring Boot and MySQL.

## [v2.0.0] - 2026-04-25

### Summary
Second version of CarQuest that adds the companion Review Service project into the same repository as a subfolder.

### Highlights

- Added `review-service/` containing the CarQuest Review Service (separate Spring Boot app on port `8081` by default).
- Refreshed the main README with review-service run steps and endpoints.
- Kept the core CarQuest business logic unchanged; this is a repository packaging/publishing update.

### Notes

The review service was previously published separately by mistake; it is now included in this repo as the intended v2 deliverable.
