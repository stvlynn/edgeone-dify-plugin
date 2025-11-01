# EdgeOne Pages

**Author:** [Steven Lynn](https://github.com/stvlynn)  
**Type:** Tool Plugin  
**Version:** 0.0.2  
**Repository:** https://github.com/stvlynn/edgeone-dify-plugin

## Description

EdgeOne Pages is a Dify plugin that enables seamless deployment of HTML content and ZIP files to Tencent EdgeOne Pages platform. This plugin provides global edge delivery capabilities, allowing you to quickly deploy and serve web content with fast, worldwide access through EdgeOne's content delivery network.

## Features

- **HTML Deployment**: Deploy HTML content directly to EdgeOne Pages with instant global access
- **ZIP File Deployment**: Upload and deploy ZIP files containing complete websites
- **Edge Delivery**: Leverage EdgeOne's global CDN for fast content delivery
- **Environment Support**: Deploy to both Production and Preview environments
- **Multi-language Support**: Full internationalization support (English, Chinese, Portuguese, Japanese)
- **Secure Authentication**: Uses EdgeOne API tokens for secure deployment

## Installation

### From Dify Marketplace
1. Open your Dify workspace
2. Navigate to Tools → Browse Marketplace
3. Search for "EdgeOne Pages"
4. Click Install and configure your credentials

### Manual Installation
1. Download the plugin package from releases
2. In Dify, go to Tools → Import Plugin
3. Upload the `.difypkg` file
4. Configure the plugin with your EdgeOne credentials

## Configuration

### Required Credentials

#### API Token (Required for ZIP deployment)
- **Purpose**: Required for ZIP file deployment to EdgeOne Pages
- **How to obtain**: 
  1. Visit [EdgeOne Console](https://console.tencentcloud.com/edgeone)
  2. Navigate to API Management
  3. Generate a new API token with Pages deployment permissions

#### Project Name (Optional)
- **Purpose**: Specify an existing EdgeOne Pages project
- **Usage**: Leave empty to create a new project automatically
- **Format**: Use existing project name from your EdgeOne console

### Plugin Setup
1. Install the EdgeOne Pages plugin
2. Go to Tools → EdgeOne Pages → Settings
3. Enter your API token (required for ZIP deployment)
4. Optionally specify a project name
5. Save configuration

## Usage Examples

### HTML Content Deployment

```markdown
Deploy this HTML content to EdgeOne Pages:

<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <h1>Hello World!</h1>
    <p>This is deployed on EdgeOne Pages</p>
</body>
</html>
```

**AI Agent Prompt:**
"Deploy this HTML code to EdgeOne Pages and give me the public URL"

### ZIP File Deployment

1. **Prepare Your Website:**
   - Create a ZIP file containing your website files
   - Ensure `index.html` is in the root of the ZIP
   - Include all assets (CSS, JS, images)

2. **Deploy via Dify:**
   - Upload your ZIP file to Dify
   - Use the "Deploy ZIP File" tool
   - Select Production or Preview environment
   - Get your public URL instantly

**AI Agent Prompt:**
"I have a website ZIP file. Deploy it to EdgeOne Pages in production environment."

### Environment Selection

- **Production**: Live deployment with full CDN capabilities
- **Preview**: Testing environment for validation before going live

## API Reference

### Deploy HTML Tool
- **Input**: HTML content (string)
- **Output**: Public URL with edge delivery
- **Authentication**: Not required

### Deploy ZIP File Tool
- **Input**: ZIP file containing website files
- **Parameters**: 
  - `zip_file`: Website ZIP file
  - `environment`: Production or Preview (default: Production)
- **Output**: Public URL with edge delivery
- **Authentication**: API token required

## Troubleshooting

### Common Issues

**"API token is required for ZIP deployment"**
- **Solution**: Configure your EdgeOne API token in plugin settings
- **Note**: HTML deployment doesn't require an API token

**"Invalid EdgeOne Pages API token"**
- **Solution**: 
  1. Verify your API token is correct
  2. Ensure the token has Pages deployment permissions
  3. Check token hasn't expired

**"Only ZIP files are supported for deployment"**
- **Solution**: Ensure your file has a `.zip` extension and is a valid ZIP archive

**"Project [name] not found"**
- **Solution**: 
  1. Verify the project name exists in your EdgeOne console
  2. Leave project name empty to create a new project automatically

**"Deployment timeout"**
- **Solution**: 
  1. Check your ZIP file size (large files take longer)
  2. Verify network connectivity
  3. Try again after a few minutes

### File Size Limits
- Maximum ZIP file size: 50MB
- Maximum individual file size: 25MB
- Recommended: Optimize images and compress assets

### Supported File Types
- HTML, CSS, JavaScript files
- Images: JPG, PNG, GIF, SVG, WebP
- Fonts: WOFF, WOFF2, TTF, OTF
- Other: JSON, XML, TXT, MD

## FAQ

**Q: Do I need an EdgeOne account?**
A: Yes, you need an EdgeOne account to obtain API tokens for ZIP deployment. HTML deployment works without an account.

**Q: Is there a free tier?**
A: EdgeOne Pages offers a free tier with limitations. Check EdgeOne pricing for details.

**Q: Can I use custom domains?**
A: Yes, EdgeOne supports custom domains. Configure them in your EdgeOne console.

**Q: How long do deployed URLs remain active?**
A: URLs remain active as long as your EdgeOne project is active. Free tier may have limitations.

**Q: Can I update an existing deployment?**
A: Yes, specify an existing project name to update deployments.

## Security & Privacy

- All deployments use HTTPS by default
- API tokens are encrypted and stored securely
- No user data is stored by the plugin
- All file transfers use secure connections

## Support

- **Documentation**: [EdgeOne Pages Documentation](https://edgeone.ai/products/pages)
- **API Reference**: [EdgeOne API Documentation](https://edgeone.ai/document/177158578324279296)
- **Issues**: Report bugs and feature requests via GitHub issues

## License

This plugin is licensed under the MIT License. See LICENSE file for details.

