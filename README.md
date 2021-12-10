# Wp Update

A minimal helper to update wordpress plugin from your own self-hosted WordPress Plugin repository.

## Install

```php
composer require springdevs/wp-update
```

## Usage

```php

add_action('init', 'update_plugin');

function update_plugin() {
    new \SpringDevs\WpUpdate\Update(
        PLUGIN_CURRENT_VERSION,
        'https://example.com/check-update',
        'plugin-dir/plugin.php'
    );
}
```

## Host API

Ensure that your `check-update` api must be return look like these example response :

```json
{
    "name": "Update Pro",
    "slug": "update-pro",
    "author": "<a href='https://springdevs.com'>SpringDevs</a>",
    "author_profile": "http://profiles.wordpress.org/springdevs",
    "version": "1.0.2",
    "homepage": "https://example.com/plugin",
    "download_url": "http://example.com/plugins/update_pro.zip",
    "requires": "3.0",
    "tested": "5.8.2",
    "requires_php": "5.3",
    "last_updated": "2021-12-09 02:10:00",
    "sections": {
        "description": "your plugin description here",
        "installation": "Click the activate button and that's it.",
        "changelog": "<ul><li>Bug fixes.</li><li>Tested up to wp-v5.8.2</li></ul>"
    },
    "banners": {
        "low": "https://plugins.svn.wordpress.org/wc-booking/assets/banner-772x250.jpg",
        "high": "https://plugins.svn.wordpress.org/wc-booking/assets/banner-772x250.jpg"
    }
}
```

**Enjoy!**