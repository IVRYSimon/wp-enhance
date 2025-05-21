version: 1
rules:
  # --- PHP Files ---
  - when: "In PHP files"
    then: |
      - Enforce PSR-12, strict types, and WP coding standards.
      - Use constructor DI; do not new‐up dependencies.
      - Prefix namespaces with `EnhanceWoo\`.
      - Avoid inline SQL; use `$wpdb->prepare()` or WC APIs.
      - Generate PHPUnit test stubs for services.

  # --- API Client ---
  - when: "Creating API client"
    then: |
      - Implement `EnhanceApiClientInterface` matching OpenAPI schema.
      - Include retry/backoff for `429` responses.
      - Map HTTP errors to specific exceptions (`EnhanceApiException`, `RateLimitException`).

  # --- Asynchronous Jobs ---
  - when: "Defining asynchronous jobs"
    then: |
      - Place in `src/Jobs/`; extend `ActionScheduler_Abstract_Job`.
      - Include proper logging and error handling.
      - Dispatch via `as_schedule_async_action()`.

  # --- Tests ---
  - when: "Writing tests"
    then: |
      - Place tests under `src/Tests/`.
      - Mock HTTP and WooCommerce dependencies.
      - Cover both success & failure scenarios.

  # --- UI Components ---
  - when: "Working on UI"
    then: |
      - Use React/Vue components in `src/UI/`.
      - Localize via `wp_set_script_translations()`.
      - Enqueue scripts/styles via proper hooks.

  # --- Translations ---
  - when: "Updating translations"
    then: |
      - Run `composer i18n:make-pot`.
      - Ensure `.pot` includes all new strings.

  # --- File Scaffolding ---
  - when: "Scaffolding new file"
    then: |
      - Add standard WP file header: plugin name, author, license.
      - Include `@since` tag with current version.
      - Auto‐generate matching PHPUnit stub under `src/Tests/`.
