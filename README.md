# Women Clothing Aggregator

A Spring Boot web application that aggregates women's clothing from two Ukrainian online stores — **JUL** and **byMe** — into a single searchable catalog.

---

## 1. What is this & how it works

The aggregator collects product data from [jul.ua](https://jul.ua) and [byme.ua](https://byme.ua) using Jsoup-based HTML parsing and stores it in a local H2 database as a cache. Users can search products by keyword and get combined results from both stores without visiting each site separately.

**Core flow:**

1. On startup (or via manual trigger), the parser fetches products from the general catalog pages of both stores and saves them to the local database.
2. The user enters a search query in the web interface.
3. The application searches the cached database and returns filtered results.
4. Each search query is saved to the search history with a timestamp.
5. Users can add products to a wishlist (liked items) for later reference.

---

## 2. Usage examples

### Search form

Enter a keyword, brand, color, or category to start searching across both stores.

![Search form](docs/screenshots/search-form.png)

### Search results

Results are displayed as a card grid with product name, price, store badge, and a link to the original page.

![Search results](docs/screenshots/search-results.png)

### Search history

Every query is logged and accessible from the History page, showing what was searched and when.

![Search history](docs/screenshots/history.png)

### Wishlist

Products can be liked and saved to the personal wishlist for quick access later.

![Wishlist](docs/screenshots/wishlist.png)

---

## 3. Tech stack

| Layer      | Technology                          |
|------------|-------------------------------------|
| Language   | Java 17                             |
| Framework  | Spring Boot 3.x                     |
| Web        | Spring Web (MVC)                    |
| Templating | Thymeleaf                           |
| ORM        | Spring Data JPA (Hibernate)         |
| Database   | H2 (file-based, persistent)         |
| Parser     | Jsoup                               |
| Utils      | Lombok                              |
| Build tool | Maven                               |