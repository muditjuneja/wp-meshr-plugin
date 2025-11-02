# Meshr - AI Internal Linking

[![WordPress Plugin](https://img.shields.io/badge/WordPress-Plugin-blue.svg)](https://wordpress.org/plugins/meshr-ai-internal-linking/)
[![License](https://img.shields.io/badge/License-GPL%20v2+-green.svg)](https://www.gnu.org/licenses/gpl-2.0.html)
[![PHP Version](https://img.shields.io/badge/PHP-7.4%2B-blue.svg)](https://www.php.net/)

AI-powered automated internal linking for WordPress. Connect your WordPress site to [Meshr](https://meshr.link) for intelligent, semantic SEO-optimized internal links.

## ✨ Features

- 🤖 **AI-Powered Semantic Linking** - Understands content meaning, not just keywords
- 🔌 **Yoast SEO & RankMath Compatible** - Works seamlessly with major SEO plugins
- 📝 **Custom Post Type Support** - Analyzes and links all your content types
- ⚡ **Bulk Link Management** - Review and approve AI suggestions in bulk
- 🚀 **2-Minute Setup** - Connect via WordPress Application Passwords, no coding required
- 🔒 **Security-First** - Proper capability checks, sanitization, and HMAC webhook verification
- 📊 **Orphan Page Detection** - Find and fix pages with zero internal links
- 🎯 **Automatic Updates** - Link changes applied directly via secure REST API

## 🚀 Quick Start

### Installation

1. **Install the plugin:**
   - Upload to `/wp-content/plugins/meshr-ai-internal-linking/`
   - Or install via WordPress admin: **Plugins → Add New → Upload Plugin**

2. **Activate the plugin** through the WordPress admin panel

3. **Generate Application Password:**
   - Go to **Users → Your Profile**
   - Scroll to **"Application Passwords"**
   - Enter name (e.g., "Meshr") and click **"Add New Application Password"**
   - Copy the generated username and password

4. **Configure in Meshr:**
   - Visit [Meshr Dashboard](https://meshr.link/dashboard)
   - Add your WordPress site with the Application Password credentials
   - Meshr will automatically discover your site and start analyzing

## 🔧 How It Works

Unlike keyword-based linkers, Meshr uses semantic AI analysis to:
1. Analyze your WordPress content for meaning and context
2. Cluster related topics and discover hidden linking opportunities
3. Suggest optimal internal linking strategies
4. Apply intelligent link updates directly to your posts and pages

**Most websites miss 60%+ of their internal linking potential** - Meshr finds them automatically.

## 📡 API Endpoints

### Health Check
```
GET /wp-json/meshr/v1/check
```
Returns site information and connectivity status. Basic authentication optional.

### Bulk Link Update
```
POST /wp-json/meshr/v1/bulk-link-update
```
Requires WordPress Application Password (Basic Auth).

**Request Body:**
```json
[
  {
    "post_id": 123,
    "from": "https://example.com/old-url",
    "to": "https://example.com/new-url"
  }
]
```

### Webhook (Optional)
```
POST /wp-json/meshr/v1/webhook
```
Requires HMAC signature verification. Configure `MESHR_WEBHOOK_SECRET` in `wp-config.php`.

## 🔐 Security

- Uses WordPress built-in Application Passwords for authentication
- Proper capability checks (`current_user_can`)
- Input sanitization on all endpoints
- HMAC-SHA256 signature verification for webhooks
- No local data storage - minimal footprint

## 📋 Requirements

- WordPress 5.0 or higher
- PHP 7.4 or higher
- WordPress Application Passwords (built-in since WordPress 5.6)

## ❓ FAQ

**Does this plugin store any data?**
No. This plugin doesn't store any data locally. It only provides REST API endpoints for Meshr to communicate with your WordPress site.

**Do I need to configure anything in WordPress?**
No admin UI is required. Just generate a WordPress Application Password in your user profile and provide it to Meshr.

**Is my site secure?**
Yes. The plugin uses WordPress's built-in authentication system (Application Passwords), proper capability checks, and sanitizes all inputs. Webhook endpoints use HMAC signature verification when enabled.

**How do I enable webhook support?**
Add this constant to your `wp-config.php`:
```php
define( 'MESHR_WEBHOOK_SECRET', 'your-secret-key-here' );
```

## 📚 Documentation

- [WordPress Documentation](https://meshr.link/wordpress/docs)
- [WordPress.org Plugin Page](https://wordpress.org/plugins/meshr-ai-internal-linking/)
- [Meshr Support](https://discord.gg/2Vpy88ghjK)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This plugin is licensed under the GPL-2.0-or-later (GNU General Public License v2.0 or later).

```
Copyright (C) 2024 Meshr

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
```

## 🔗 Links

- [Meshr Website](https://meshr.link)
- [WordPress.org Plugin](https://wordpress.org/plugins/meshr-ai-internal-linking/)
- [Discord Support](https://discord.gg/2Vpy88ghjK)

---

Made with ❤️ by [Meshr](https://meshr.link)

