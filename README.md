# How PSFree Offline Caching Works

PSFree implements offline caching using **HTML5 Application Cache**, allowing the exploit to function without an internet connection after initial setup.

> **Important**: You must cache PSFree while online before attempting to use it offline. Follow the testing instructions below to properly set up offline functionality.

## Implementation Details

The offline caching system uses several key components:

- **Cache Manifest File** - Lists all required resources to be cached
- **Application Cache API** - Manages the caching process
- **User Interface** - Provides status indicators and control button

## Cache Status Events

The application monitors several cache events to keep users informed:

- `checking` - Verifying the manifest
- `downloading` - Downloading resources
- `progress` - Resource download progress
- `cached` - Caching successfully completed
- `updateready` - New version available
- `error` - Caching error occurred

**Updates**: The script can be updated and supplemented regularly. You will always have an up-to-date working version.

## Testing Offline Functionality on PS4

### Initial Setup (Online)

1. Open the PSFree exploit page on your PS4 browser while connected to the internet
2. Click the **"Cache for Offline Use"** button
3. Wait for the cache process to complete - the status indicator will display *"Cached and Ready for Offline Use"*
4. Once caching is complete, you'll see a confirmation message

> **Note**: The first time you run the exploit after caching, it should still be with an internet connection to verify everything works properly.

### Testing Offline Mode

1. After successful caching, disconnect your PS4 from the internet (disable Wi-Fi or disconnect Ethernet)
2. Close and reopen the PS4 browser
3. Navigate to the PSFree exploit URL (it should load from cache)
4. Verify that the page loads with a status indicator showing *"Offline Mode (Cached)"*
5. The exploit should run automatically as normal

### Testing After PS4 Reboot

1. Power off your PS4 completely
2. Power on your PS4, but do not connect to the internet
3. Open the PS4 browser and navigate to the PSFree URL
4. The page should load from cache and the exploit should run normally

## Troubleshooting

If you encounter issues with offline functionality:

- **Cache not working**: Reconnect to the internet, reload the page, and click *"Recache Resources"*
- **Page won't load offline**: Your cache may have been cleared. You need to reconnect and cache the exploit again
- **Exploit fails in offline mode**: Ensure you've cached the most recent version with a working internet connection first
- **Update available**: If you see *"Cache update available"*, connect to the internet and click *"Apply Update"*

## Visual Indicators

The PSFree interface now includes several visual indicators to help you understand the current status:

- **OFFLINE Badge**: Appears when you're disconnected from the internet
- **CACHED Badge**: Appears when you're offline but have successfully cached resources
- **Console Highlighting**: Different message types are now color-coded for better readability
- **Stage Progress**: Exploit stages now show clearer progress indicators

## Technical Details

### Cache Size and Limitations

The PS4 browser typically allows around **50MB** of application cache storage. PSFree's resources including the binary payload require approximately **2-3MB** of cache, well within the limit.

### Cache Versioning

The cache manifest includes a version comment line. When the manifest is updated (e.g., when files change or new versions are released), the browser will detect the change and refresh the cache with the new content.

### PS4/PS5 Browser Compatibility

The PS4/PS5 browsers are based on **WebKit** and support HTML5 Application Cache. The implementation has been optimized specifically for these browsers' rendering engines and memory constraints. The enhanced UI provides a better visual experience while maintaining full compatibility.

## Security Considerations

Cached resources are stored locally on your PS4. No data is sent back to servers when running in offline mode. This implementation ensures the exploit runs entirely on your device without external connections.
