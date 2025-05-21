# Plugin Architecture & Coding Standards

## 1. Overview
A concise blueprint for organizing your plugin codebase, enforcing consistency, and ensuring maintainability.

## 2. File & Directory Layout
enhance-woocommerce/
├── composer.json
├── enhance-woocommerce.php # Plugin header & lifecycle hooks
├── bootstrap.php # Registers service container
├── src/
│ ├── Admin/ # Settings pages & admin controllers
│ ├── Core/ # Plugin core class, bootstrapping
│ ├── Domain/ # Entities (HostingPackage, Subscription)
│ ├── Events/ # Custom event definitions
│ ├── Http/
│ │ ├── Client/ # HTTP client implementation
│ │ └── Gateway/ # Client interfaces & factories
│ ├── Jobs/ # Async tasks (Action Scheduler)
│ ├── Logging/ # LoggerInterface & implementations
│ ├── ServiceProvider/ # DI container & registrations
│ ├── Tests/ # PHPUnit unit & integration tests
│ ├── UI/ # React/Vue components or PHP templates
│ ├── Utils/ # Utility traits and helpers
│ └── WooCommerce/ # WC hooks, filters, order handling
├── assets/ # js/, css/
├── languages/ # .pot/.po/.mo files
├── templates/ # Frontend .php templates
└── .github/workflows/ # CI/CD definitions



## 3. PHP Coding Standards
- **WordPress + PSR-12**  
- `declare(strict_types=1);` in every file  
- Tabs for indentation; spaces around operators/braces  
- Multiline arrays with trailing commas  
- Sanitization/Escaping:
  - `sanitize_text_field()`, `esc_html()`, `esc_url()`
  - `wp_kses_post()`, `absint()`, `floatval()`, `sanitize_key()`

## 4. JavaScript Standards
- Vanilla JS or minimal jQuery  
- ES6+ syntax, transpiled via `@wordpress/scripts`  
- Follow [WP JS coding standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/javascript/)

## 5. Documentation
- PHPDoc (`@since`, `@param`, `@return`, `@throws`) on all classes/methods  
- Inline comments for complex logic  
