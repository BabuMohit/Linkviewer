# Website Screenshot Carousel v2.0 - Chrome Extension

A powerful Chrome extension that intelligently detects content-relevant links and displays their screenshots in an interactive, searchable carousel format.

## 🆕 What's New in v2.0

### ✨ Enhanced Features
- 🔍 **Smart Search** - Find specific links instantly with built-in search
- 📏 **Resizable Interface** - Drag to adjust popup size to your preference  
- 🎯 **Intelligent Link Detection** - Focuses on academic/content links, ignores navigation
- ⚡ **Enhanced Performance** - Advanced caching and memory management
- 🎨 **Improved UI** - Better controls, visual feedback, and user experience
- 🔄 **Advanced Filtering** - Toggle between filtered and all links view

### 🎓 Perfect For
- **Students & Researchers** - Preview academic papers and references
- **Developers** - Quick access to documentation and technical resources
- **Content Creators** - Research and fact-checking workflows
- **General Users** - Enhanced browsing experience on content-heavy sites

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/BabuMohit/Linkviewer.git
cd Linkviewer

# Install dependencies
npm install

# Start the screenshot service
npm start
# OR on Windows:
run_server.bat
```

### Load Extension in Chrome
1. Open Chrome and go to `chrome://extensions/`
2. Enable "Developer mode" (top right toggle)
3. Click "Load unpacked"
4. Select this project folder
5. The extension icon should appear in your toolbar

## 📋 Key Features

### 🧠 Smart Link Detection
- **Content-Focused**: Detects academic references, citations, and inline content links
- **Noise Filtering**: Automatically ignores navigation menus, ads, and UI elements
- **Context-Aware**: Understands different website structures (Wikipedia, blogs, documentation)

### 🎨 Enhanced User Interface
- **Search Functionality**: Instantly find specific links by typing keywords
- **Resizable Popup**: Drag corners to adjust size for your workflow
- **Multiple View Modes**: Toggle between filtered content links and all links
- **Smart Navigation**: Jump buttons for quick access to specific screenshots

### ⚡ Performance & Reliability
- **Advanced Caching**: Screenshots cached for faster subsequent loads
- **Memory Management**: Automatic cleanup prevents browser slowdown
- **Error Recovery**: Robust error handling with retry mechanisms
- **Optimized Processing**: Efficient link detection and screenshot generation

## 📁 Project Structure

### Core Files
- `manifest.json` - Extension configuration (Manifest V3)
- `popup.html` - Enhanced UI layout with search and resize
- `popup.js` - Advanced functionality with state management
- `content.js` - Intelligent link detection and filtering
- `server.js` - Screenshot service with error handling
- `cache-manager.js` - Dedicated cache management system
- `package.json` - Node.js dependencies and scripts

## 🔧 Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- Chrome browser
- Internet connection for initial setup

### Step-by-Step Installation

1. **Download the extension**
   ```bash
   git clone https://github.com/BabuMohit/Linkviewer.git
   cd Linkviewer
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the screenshot service**
   ```bash
   npm start
   ```
   Or on Windows, double-click `run_server.bat`

4. **Load extension in Chrome**
   - Open `chrome://extensions/`
   - Enable Developer mode
   - Click "Load unpacked"
   - Select the project folder

5. **Test the extension**
   - Visit any webpage with links (try Wikipedia or a news article)
   - Click the extension icon
   - Wait for screenshots to load and try the search feature

## 🎯 Usage Guide

### Basic Usage
1. **Navigate to any webpage** with external links
2. **Click the extension icon** in your Chrome toolbar
3. **Wait for link detection** - The extension will intelligently scan the page
4. **Browse screenshots** - Use navigation controls or search functionality
5. **Resize as needed** - Drag the popup corners to adjust size

### Advanced Features

#### 🔍 Search Functionality
- Type keywords in the search box to filter links instantly
- Search works on both link text and URLs
- Clear search to return to full results

#### 📏 Resizable Interface
- Drag any corner of the popup to resize
- Size preference is remembered for your session
- Optimize for your screen size and workflow

#### 🎛️ View Controls
- **Link Toggle**: Switch between showing link numbers or names
- **Filter Toggle**: Show only content links vs. all links
- **Zoom Controls**: Adjust screenshot preview size
- **Jump Buttons**: Quick navigation to specific screenshots

## 🌟 Real-World Examples

### Wikipedia Research
- Automatically detects reference links and citations
- Preview academic papers and sources without leaving the article
- Search for specific topics within the references

### News Article Fact-Checking
- Identifies source links within article content
- Quick preview of referenced studies and reports
- Filter out social media and navigation links

### Technical Documentation
- Focuses on relevant documentation links
- Preview API references and related guides
- Resize interface to work alongside your IDE

## ⚙️ Configuration

### Server Settings
The screenshot service runs on port 5000 by default. To change:
1. Edit `server.js` and modify the PORT variable
2. Update `popup.js` to match the new port
3. Update `manifest.json` host_permissions if needed

### Screenshot Quality
Modify Puppeteer settings in `server.js`:
```javascript
await page.setViewport({ width: 1280, height: 720 });
```

### Link Detection Customization
Adjust content selectors in `content.js` for specific website types:
```javascript
const contentSelectors = [
    'article', 'main', '.content',
    '.post-content', '.entry-content'
];
```

## 🐛 Troubleshooting

### Extension Not Working
- **Check Server**: Ensure screenshot service is running at `http://localhost:5000`
- **Reload Extension**: Disable and re-enable in `chrome://extensions/`
- **Check Console**: Open DevTools (F12) and look for error messages
- **Refresh Page**: Reload the webpage you're testing on

### No Screenshots Appearing
- **Server Status**: Visit `http://localhost:5000/health` - should show "Service is running"
- **Website Blocking**: Some sites block screenshot generation
- **Network Issues**: Check for CORS or connectivity errors in console
- **Port Conflicts**: Ensure port 5000 is available

### Search Not Working
- **Clear Search**: Click the clear button or delete search text
- **Case Sensitivity**: Search is case-insensitive, try different keywords
- **Link Content**: Search works on visible link text and URLs

### Performance Issues
- **Memory Usage**: Restart Chrome if extension becomes slow
- **Cache Clearing**: Clear browser cache if screenshots seem outdated
- **Link Limits**: Extension automatically limits links to prevent overload

## 🔒 Privacy & Security

### Local Processing
- **No External Servers**: All screenshots generated locally on your machine
- **No Data Collection**: Extension doesn't send any data to external services
- **Secure Communication**: Uses localhost-only communication between components
- **Temporary Storage**: Screenshots cached temporarily for performance only

### Permissions Explained
- **activeTab**: Access current webpage content for link detection
- **scripting**: Execute content scripts for link analysis
- **storage**: Cache screenshots for better performance
- **localhost:5000**: Communicate with local screenshot service

## 🚧 Known Limitations

### Current Limitations
- **Chrome Only**: Currently supports Chrome browser only
- **Local Server Required**: Needs Node.js server running for screenshots
- **Some Sites Block Screenshots**: Certain websites prevent automated screenshot capture
- **Windows Batch File**: `run_server.bat` is Windows-specific (use `npm start` on other OS)

### Acceptable Behaviors
- **Popup Closes on Click**: Chrome limitation - popup closes when clicking outside
- **Loading Time**: Initial screenshot generation takes 1-3 seconds per link
- **Memory Usage**: Uses 100-200MB RAM during active screenshot generation

## 🔄 Version Comparison

### v2.0 (Current) vs v1.0

| Feature | v1.0 | v2.0 |
|---------|------|------|
| **Link Detection** | All links on page | Smart content-focused filtering |
| **User Interface** | Fixed size popup | Resizable with search functionality |
| **Performance** | Basic caching | Advanced cache management |
| **Navigation** | Simple prev/next | Jump buttons + search + filters |
| **Error Handling** | Basic try-catch | Comprehensive error recovery |
| **Memory Management** | None | Automatic cleanup and optimization |

## 🤝 Contributing

### Development Setup
1. Fork the repository
2. Clone your fork locally
3. Install dependencies: `npm install`
4. Start development server: `npm run dev`
5. Load extension in Chrome developer mode

### Code Style
- Use consistent indentation (2 spaces)
- Add comments for complex logic
- Follow existing naming conventions
- Test on multiple website types

### Submitting Changes
1. Create a feature branch
2. Make your changes with clear commit messages
3. Test thoroughly on different websites
4. Update documentation if needed
5. Submit a pull request with detailed description

## 📝 License

This project is open source. Feel free to use, modify, and distribute according to the license terms.

## 🆘 Support

### Getting Help
- **Documentation**: Check this README and inline code comments
- **Issues**: Report bugs and feature requests on GitHub
- **Troubleshooting**: Follow the troubleshooting guide above
- **Development**: Check the contributing section for development setup

### Reporting Issues
When reporting issues, please include:
1. **Steps to reproduce** the problem
2. **Expected vs actual behavior**
3. **Browser version** and operating system
4. **Console error messages** (if any)
5. **Website URL** where issue occurred (if applicable)

---

**Version**: 2.0.0  
**Last Updated**: 2024  
**Compatibility**: Chrome 88+, Node.js 14+

🌟 **Star this repo if you find it useful!** 