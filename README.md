# Website Screenshot Carousel - Chrome Extension

A Chrome extension that detects links on web pages and displays their screenshots in an interactive carousel format.

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

## 📋 Features

- **Automatic Link Detection**: Scans web pages for external links
- **Screenshot Generation**: Creates previews of linked websites
- **Interactive Carousel**: Navigate through screenshots with controls
- **Local Processing**: All screenshots generated locally for privacy
- **Cross-Platform**: Works on any website

## 🛠️ How It Works

1. **Content Script** (`content.js`) - Detects links on the current page
2. **Popup Interface** (`popup.html` + `popup.js`) - Displays the carousel UI
3. **Screenshot Service** (`server.js`) - Generates website screenshots using Puppeteer
4. **Local Server** - Runs on `http://localhost:5000`

## 📁 Project Structure

```
├── manifest.json       # Extension configuration
├── popup.html         # Extension popup UI
├── popup.js          # Popup logic and carousel
├── content.js        # Link detection script
├── server.js         # Screenshot generation service
├── package.json      # Node.js dependencies
├── run_server.bat    # Windows server startup
└── README.md         # This file
```

## 🔧 Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- Chrome browser
- Internet connection for initial npm install

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
   - Visit any webpage with links
   - Click the extension icon
   - Wait for screenshots to load

## 🎯 Usage

1. **Navigate to any webpage** with external links
2. **Click the extension icon** in your Chrome toolbar
3. **Wait for link detection** - The extension will scan the page
4. **View screenshots** - Navigate through the carousel using arrow buttons
5. **Click screenshots** to visit the linked websites

## ⚙️ Configuration

### Server Port
The screenshot service runs on port 5000 by default. To change this:

1. Edit `server.js` and change the port number
2. Update `popup.js` to match the new port
3. Update `manifest.json` host_permissions if needed

### Screenshot Quality
Modify the Puppeteer settings in `server.js`:
```javascript
await page.setViewport({ width: 1280, height: 720 });
```

## 🐛 Troubleshooting

### Extension Not Working
- Check if the server is running (`http://localhost:5000`)
- Reload the extension in `chrome://extensions/`
- Check browser console for errors

### No Screenshots Appearing
- Verify server is accessible
- Check if websites block screenshots (some do)
- Look for CORS or network errors in console

### Server Won't Start
- Ensure Node.js is installed
- Run `npm install` to install dependencies
- Check if port 5000 is available

## 🔒 Privacy & Security

- **Local Processing**: All screenshots are generated locally
- **No Data Collection**: Extension doesn't send data to external servers
- **Temporary Storage**: Screenshots are cached temporarily for performance
- **Secure Communication**: Uses localhost for extension-server communication

## 🚧 Known Limitations

- Some websites block screenshot generation
- Requires local server to be running
- Limited to Chrome browser
- May not work with dynamic/JavaScript-heavy sites

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

This project is open source. Feel free to use and modify as needed.

## 🆘 Support

If you encounter issues:
1. Check the troubleshooting section above
2. Look for error messages in Chrome DevTools
3. Ensure all dependencies are installed
4. Verify the server is running properly

---

**Version**: 1.0.0  
**Last Updated**: 2024
