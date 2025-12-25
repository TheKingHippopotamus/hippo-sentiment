# Hippo-Sentiment

A production-ready microservice for scraping AI-generated stock summaries . Built with Flask, Selenium, and modern web technologies.

# TRY IT OUT (;  
===================================================
# https://hippo-sentiment-975377229992.us-south1.run.app/
===================================================
## Overview

This microservice provides a RESTful API and web interface for automatically scraping AI-generated stock summaries from MarketBeat. It uses Selenium WebDriver to access MarketBeat, locate AI summary b[...] 

### Screenshots

![Web UI - Main Interface](example1.png)
*Main search interface with ticker input and results display*

![Web UI - Results View](example2.png)
*Scraped results with sentiment highlighting and download options*

![Web UI - PDF Preview](example3.png)
*PDF preview modal before download*

![Web UI - Mobile View](example4.png)
*Responsive mobile interface*

## Key Features

### Core Functionality
- **RESTful API** - Simple and clear endpoints for scraping operations
- **Web UI** - Modern, responsive web interface with PWA support
- **PDF Generation** - Generate and download PDF reports with preview functionality
- **Ticker Logos** - Automatic display of stock ticker logos in UI and PDFs
- **Structured Data Parsing** - Automatic parsing of text into structured JSON (sentiment items, metadata)
- **Download Options** - Download as JSON, TXT, or both (ZIP)

### Technical Features
- **Error Handling** - Specific HTTP status codes (400, 404, 504, 500)
- **Input Validation** - Ticker symbol validation
- **Rate Limiting** - Built-in rate limiting to prevent abuse
- **Audit Logging** - Comprehensive audit logs with request tracking
- **Caching** - Metadata caching to reduce redundant operations
- **Docker Support** - Easy deployment with containers
- **Flexible Configuration** - Environment variable support
- **PWA Support** - Progressive Web App capabilities for mobile devices

### Privacy & Security
- **Privacy-First** - Server stores only metadata, never content
- **Request Tracking** - Unique request IDs for all operations
- **Audit Trail** - Complete audit logging of all requests

## Project Structure

The project is organized into logical layers:

```
service_scraping/
├── api/                    # API layer - Flask endpoints
│   ├── routes/             # Route handlers
│   │   ├── health.py       # Health check endpoint
│   │   ├── scrape.py       # Scraping endpoints
│   │   └── web.py          # Web UI routes
│   ├── app.py              # Flask application factory
│   └── wsgi.py             # WSGI entry point for production
├── core/                   # Business logic layer
│   └── scraper.py          # Core scraping logic
├── infrastructure/         # Infrastructure components
│   ├── logger.py           # Logging configuration
│   ├── audit_logger.py     # Audit logging
│   ├── cache.py            # Caching system
│   └── load_driver.py      # Selenium driver management
├── service/                 # Service layer
│   └── scrape_handler.py    # Scraping request handler
├── config/                 # Configuration
│   ├── config.yaml         # Configuration file
│   └── config.py           # Configuration loader
├── utils/                  # Utility functions
│   ├── validation.py       # Input validation
│   ├── exceptions.py       # Custom exceptions
│   ├── text_parser.py      # Text parsing utilities
│   └── paths.py            # Path resolution
├── web_ui/                 # Web interface
│   ├── static/             # Static assets
│   │   ├── css/            # Stylesheets
│   │   ├── js/             # JavaScript
│   │   └── *.png           # Images and icons
│   └── templates/          # HTML templates
│       └── index.html      # Main UI template
├── tests/                  # Test suite
├── logs/                   # Log files
├── output/                  # Output directory (optional)
├── Dockerfile              # Docker configuration
├── requirements.txt         # Python dependencies
├── run.py                  # Local development entry point
└── railway.json            # Railway deployment config
```



### Main Features

- **Search Interface** - Enter ticker symbols to scrape data
- **Results Display** - View scraped content with sentiment highlighting
- **Ticker Logos** - Automatic display of stock logos
- **Download Options** - Download as JSON, TXT, or PDF
- **PDF Preview** - Preview PDF before downloading
- **Search History** - View and reuse recent searches
- **Responsive Design** - Works on desktop and mobile devices
- **PWA Support** - Install as Progressive Web App




### PDF Generation

- **Preview Modal** - Preview PDF content before download
- **Direct Download** - No print dialog, direct file download
- **Multi-page Support** - Automatic page breaks for long content
- **Ticker Logo** - Includes ticker logo in PDF header
- **Structured Layout** - Professional formatting with sentiment analysis

### Project Structure Guidelines

- **api/** - API endpoints and routing
- **core/** - Business logic (scraping operations)
- **infrastructure/** - Technical components (logging, caching, drivers)
- **service/** - Service layer (request handling)
- **config/** - Configuration management
- **utils/** - Utility functions
- **web_ui/** - Frontend assets and templates


## HTTP Status Codes

- **200** - Success
- **400** - Invalid input (InvalidTickerError)
- **404** - Summary not found (SummaryNotFound)
- **504** - Scraping timeout (ScraperTimeout)
- **500** - Internal server error

## Response Headers

All responses include:
- `X-Request-ID` - Unique request identifier
- `X-Request-Duration` - Processing duration (seconds)

## Error Handling

The service uses a custom exception hierarchy:

```
ScrapingError (base)
├── SummaryNotFound → HTTP 404
├── ScraperTimeout → HTTP 504
└── InvalidTickerError → HTTP 400
```


## Privacy & Security

- **No Content Storage** - Server never stores scraped content
- **Metadata Only** - Only request metadata is logged
- **Rate Limiting** - Built-in protection against abuse
- **Request Tracking** - All requests are tracked with unique IDs


### Recent Updates

- Added PDF preview functionality
- Implemented ticker logo display in UI and PDFs
- Added CORS-safe proxy endpoint for ticker logos
- Improved mobile responsiveness
- Added PWA support
- Enhanced error handling and logging

### Add Hippo to HomeScreen 👮

**Safari**

![Add Hippo to Home Screen - Safari]("Safari_1.png)
*Tap the share icon and then choose "Add to Home Screen" in Safari.*

**Chrome**

![Add Hippo to Home Screen - Chrome](Chrome1.png)
*Open the browser menu and select "Add to Home screen" in Chrome.*

**Both Browsers**

![Home Screen Step 1](2.png)
![Home Screen Step 2](3.png)
![Home Screen Step 3](4.png)

![Done - Hippo on Home Screen](Done.png)

# Made With 🫀 By - 
# TheKingHippopotamus 
