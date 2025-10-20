# SharePoint Best Practices Documentation

This website is built using [Docusaurus](https://docusaurus.io/) and deployed to Cloudflare Workers on the `/spdockit-consultant` route at `docs.syskit.com/spdockit-consultant`.

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Local development
npm start

# Build for production
npm run build

# Deploy to Cloudflare Workers
npm run deploy
```

## 📦 Deployment

### Production Deployment
```bash
npm run deploy:production
```

### Staging Deployment
```bash
npm run deploy:staging
```

### Local Testing with Cloudflare Workers
```bash
npm run dev
```

Then visit: **`http://127.0.0.1:8787/spdockit-consultant`**

## 🔧 Configuration

- **Production**: `https://docs.syskit.com/spdockit-consultant` ✅ **Working**
- **Staging**: `https://docs-staging.syskit.com/spdockit-consultant` ✅ **Working**
- **Route**: `/spdockit-consultant/*`
- **Worker**: Serves the Docusaurus site with proper routing and caching

### URLs:
- **Production**: `https://docs.syskit.com/spdockit-consultant` ✅ **Live**
- **Staging**: `https://docs-staging.syskit.com/spdockit-consultant` ✅ **Live**

## 📁 Project Structure

- `src/worker.js` - Cloudflare Worker script
- `wrangler.toml` - Worker configuration
- `docs/` - Documentation content
- `build/` - Generated static files

## 🛠️ Development

### Local Development

```bash
npm start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

### Build

```bash
npm run build
```

This command generates static content into the `build` directory.
