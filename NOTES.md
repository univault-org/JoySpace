# Media Bookmarks - Technical Notes

## Overview
A tool for managing local video bookmarks, designed specifically for VS Code users with Live Server extension.

## Flow

### Initial Setup
1. User selects folder with videos
2. Tool generates markdown with:
   - Video paths (relative to project)
   - Metadata (title, duration, tags, etc.)
   - Thumbnails (if needed)
3. Save markdown file in project

### Playing Videos
1. User must:
   - Open project in VS Code
   - Start Live Server extension
   - Open the HTML file via Live Server

2. When clicking video thumbnail:
   - Video plays through Live Server
   - No need to select file each time
   - Avoids browser security restrictions
   - Better performance (streams instead of loading full file)

## Technical Requirements
- VS Code
- Live Server extension
- Modern browser
- Local video files

## Limitations & Solutions
### Browser Security
- ❌ Can't access local files directly
- ✅ Solution: Use Live Server to serve files

### File Access
- ❌ Can't persist file access permissions
- ✅ Solution: Serve through localhost

### Performance
- ✅ Streams video instead of loading full file
- ✅ Only loads metadata initially
- ✅ Better memory management

## Best Practices
1. File Organization:
   ```
   project/
   ├── index.html
   ├── bookmarks.md
   ├── videos/
   │   ├── video1.mp4
   │   └── video2.mp4
   └── thumbnails/
       ├── thumb1.jpg
       └── thumb2.jpg
   ```

2. Relative Paths:
   - Use relative paths in markdown
   - Makes project portable
   - Works with Live Server

3. Markdown Structure:
   ```markdown
   # Video Collection

   ## video1.mp4
   - Path: ./videos/video1.mp4
   - Title: Tutorial Video
   - Duration: 10:30
   - Tags: tutorial, coding
   - Notes: Important points at 2:30
   ```

## Development Notes
- Keep video files in project directory
- Use relative paths for portability
- Consider thumbnail generation
- Save user preferences in markdown