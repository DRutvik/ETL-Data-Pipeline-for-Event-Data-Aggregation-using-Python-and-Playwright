# Etix Event Data Pipeline

## Project Story

During my freelance contract as a data engineer for a US-based music analytics startup, I was tasked with building an automated pipeline to extract, enrich, and structure live event data from Etix—a major US ticketing platform. This project was crucial for powering the company’s internal analytics and event recommendation systems.

---

### Motivation

The company needed timely, structured data on thousands of music events (title, date, venue, location, ticket price, image, and more) to support downstream analytics and business logic. Since Etix does not provide a public API, the only solution was robust, large-scale web scraping and data enrichment.

---

### Key Challenges

- **No Public API:** All data extraction had to be performed by scraping dynamic web pages.
- **Dynamic Loading:** Events are loaded with “Show More” buttons via JavaScript, requiring headless browser automation.
- **Frequent UI Changes:** Selectors/DOM structure were prone to changes, so the solution had to be adaptable.
- **Venue Data Ambiguity:** City and state fields sometimes ambiguous or duplicated, requiring custom cleaning and validation.
- **Anti-bot Protections:** Needed to carefully pace scraping to avoid being blocked.

---

### Solution & Approach

- **Playwright Automation:** Automated navigation, search, and dynamic “Show More” loading with Playwright.
- **HTML Parsing:** Extracted structured event and venue details with BeautifulSoup.
- **Geocoding Integration:** Used Nominatim to enrich venues with latitude/longitude and standardized addresses.
- **Deduplication:** Ensured unique event and venue records.
- **Error Handling:** Script gracefully handles timeouts, incomplete records, and layout changes.

---

### Results & Impact

- Automated the collection and normalization of hundreds of live US events weekly.
- Reduced manual data entry by over 95% for analytics and content teams.
- Delivered clean, deduplicated event data ready for loading into analytics databases.

---

### Tech Stack

- **Python:** Playwright, BeautifulSoup, Requests
- **Scheduling:** Custom scripts (can be adapted for Airflow/Cron)
- **Data Output:** CSV, ready for warehouse ingestion (e.g., Supabase, BigQuery)
- **Platform:** macOS/Linux

---

## Code Availability

> **Due to company confidentiality, the full code is not open source.**  
> If you are a hiring manager or technical collaborator and wish to see a code sample,  
> please contact me. I’m happy to discuss the pipeline architecture or share representative code in a private setting.

---

## Lessons Learned

- Web scraping for production analytics is an ongoing process—robust error handling and adaptability are key.
- Free/open mapping and geocoding tool

## Interested in how I built this or want to see code samples?
Connect with me on [LinkedIn](https://www.linkedin.com/in/rutvik09/) or email [rutvikdeshmukh5@gmail.com].
