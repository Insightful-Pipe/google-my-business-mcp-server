# Google My Business MCP Server (Google Business Profile) by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/google-my-business)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Google My Business to AI assistants for local SEO analytics and business profile management.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — The Google My Business MCP server enables Claude, ChatGPT, Cursor, and other AI assistants to analyze your Google Business Profile performance. Track local search visibility, monitor reviews, manage posts, and optimize your local presence.

[![Explore All MCP Servers](https://img.shields.io/badge/Explore_All-MCP_Servers-blue?style=for-the-badge)](https://insightfulpipe.com/mcp-servers)

![Google My Business MCP Server](https://insightfulpipe.com/images/google-business-icon.svg)

## MCP Server URL

```
https://google-my-business.insightfulmcp.com/
```

## What is Google My Business MCP?

Google My Business MCP is a **remote Model Context Protocol server** that connects your Google Business Profile to AI assistants. This local SEO integration allows you to:

- Query local search performance using natural language
- Analyze Google Maps visibility and actions
- Track review sentiment and respond to reviews
- Manage local posts, photos, and media
- Get AI recommendations for profile optimization

## Installation

### Claude

1. Copy the MCP Server URL: `https://google-my-business.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** and sign in to InsightfulPipe if asked. Claude then lists the connector as connected.

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://google-my-business.insightfulmcp.com/`
3. Sign in to InsightfulPipe if asked. The connection finishes as soon as you are signed in.

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http google-my-business https://google-my-business.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "google-my-business": {
      "url": "https://google-my-business.insightfulmcp.com/"
    }
  }
}
```

When Cursor shows **Needs authentication**, click **Connect** and sign in to InsightfulPipe if asked.

## Available Actions

25 actions: 16 read, 9 write.

### Read Actions (16)

| Action | Description |
|--------|-------------|
| `get_attributes` | Fetch Google-updated attributes for a location |
| `get_available_attributes` | List attributes available for a category/region (use categoryName, regionCode, languageCode params) |
| `get_batch_categories` | Get service types for specific category IDs (use names, regionCode, languageCode, view params) |
| `get_categories` | List categories with predefined services (use regionCode, languageCode, filter, view params) |
| `get_daily_metrics` | Daily metric time series for a single metric |
| `get_food_menus` | Get current food menus for a location |
| `get_local_post` | Retrieve one exact LocalPost by its full resource name |
| `get_local_posts` | Retrieve local posts created for a location |
| `get_location_attributes` | Get current attributes for a location |
| `get_location_details` | Retrieve metadata for the specified location |
| `get_media` | List media (photos/videos) for a location |
| `get_multi_daily_metrics` | Fetch multiple daily metrics in a single call |
| `get_reviews` | List customer reviews |
| `get_search_keywords` | Monthly search keyword impression counts |
| `get_services` | Get services for a location (use readMask=serviceItems param) |
| `get_verifications` | List verification attempts for a location |

### Write Actions (9)

| Action | Description |
|--------|-------------|
| `create_local_post` | Create event, offer, or call-to-action posts |
| `create_media` | Upload photo or video from URL |
| `delete_local_post` | Delete one exact LocalPost by its full resource name |
| `delete_media` | Delete a media item |
| `delete_review_reply` | Delete a reply to a specific review |
| `reply_to_review` | Reply to a specific review or update existing reply |
| `start_media_upload` | Start media upload from bytes (returns resourceName for upload) |
| `update_food_menus` | Update food menus with items, nutrition, dietary info, photos |
| `update_local_post` | Edit one exact LocalPost by its full resource name |

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

## Usage Examples

### Profile Performance

```
"How is my Google Business Profile performing this month?"
```

### Review Management

```
"Show me my recent reviews and help me reply to them"
```

### Search Keywords

```
"What search terms are people using to find my business?"
```

### Create Post

```
"Create a local post about our weekend sale with 20% off"
```

### Action Tracking

```
"How many direction requests did I get this week?"
```

## Supported Metrics

| Metric | Description |
|--------|-------------|
| Search Views | Times shown in Google Search |
| Maps Views | Times shown in Google Maps |
| Website Clicks | Clicks to your website |
| Direction Requests | Navigation requests |
| Phone Calls | Click-to-call actions |
| Total Reviews | Review count |
| Average Rating | Star rating average |
| Photo Views | Business photo views |

## Why Google My Business MCP?

### For Local Businesses
- **Visibility tracking** - Understand local search presence
- **Review management** - Monitor and respond to reviews with AI help
- **Action optimization** - Drive more calls and visits

### For Multi-Location Brands
- **Location comparison** - Compare store performance
- **Centralized analytics** - All locations in one view
- **Review monitoring** - Track reputation at scale

### For Agencies
- **Client reporting** - Local SEO performance reports
- **Multi-account management** - Handle multiple businesses
- **Content creation** - Create posts for clients

## Security & Privacy

- **Official Google Business Profile API** - Direct integration with Google's API
- **OAuth 2.0** - Secure Google authentication
- **Granular permissions** - Control read vs write access

## Pricing

The Google My Business MCP server is included in every InsightfulPipe plan, together with all other MCP servers and the CLI. Plans start at $29.99/month, and you can try it for 7 days. See [insightfulpipe.com/pricing](https://insightfulpipe.com/pricing) for current plans.

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers for marketing and analytics.

### Google MCP Servers
- [Google Search Console MCP](https://insightfulpipe.com/mcp-servers/google-search-console) - SEO analytics
- [Google Analytics MCP](https://insightfulpipe.com/mcp-servers/google-analytics) - Website analytics
- [Google Ads MCP](https://insightfulpipe.com/mcp-servers/google-ads) - Advertising
- [PageSpeed MCP](https://insightfulpipe.com/mcp-servers/pagespeed) - Core Web Vitals

### SEO Tools MCP Servers
- [Web Crawler MCP](https://insightfulpipe.com/mcp-servers/crawler) - SEO auditing
- [Screenshot MCP](https://insightfulpipe.com/mcp-servers/screenshot) - Visual capture

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs/connectors-google-business-profile)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
