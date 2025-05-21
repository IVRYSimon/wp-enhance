Custom CORS header for API
TIP

This is an advanced feature for experienced developers and is not required in normal operation.

This feature requires Enhance 12.1.0 or higher.

If you are creating a custom UI for Enhance running on a different domain, you may experience cross-origin issues. To resolve this, you can have the Enhance API send a custom Access-Control-Allow-Origin header which should permit the web browser to access the Enhance API from the 3rd party domain.

To activate this feature:

On the control panel server, create a file at /var/local/enhance/orchd/custom.cors and enter your origin URL for example https://my-custom-enhance-dashboard.com

Run systemctl restart orchd
