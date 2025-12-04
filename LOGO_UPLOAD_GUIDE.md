# Logo Upload Feature Guide

## Overview
The admin panel now includes a comprehensive logo management system with **automatic image compression** that allows you to customize the branch logo and name displayed in the website header.

## Features

### 1. Logo Upload with Auto-Compression ✨
- **Location**: Admin Panel → Settings Tab
- **File Requirements**:
  - **No size limit!** Images are automatically compressed
  - Supported formats: PNG, JPG, JPEG, SVG, GIF, WebP
  - Auto-compressed to: Max 200KB, 400x400px
  - High quality maintained (90% quality setting)
  - Automatic conversion to PNG for best quality
  
### 2. Branch Name Customization
- **Location**: Admin Panel → Settings Tab
- **Default**: "Mechanical AI"
- **Usage**: The name appears next to the logo in the header

## How It Works

### Step 1: Access Admin Panel
1. Log in with admin credentials
2. Navigate to `/admin` route
3. Click on the **Settings** tab (second tab after Dashboard)

### Step 2: Upload Logo (with Auto-Compression)
1. In the "Branch Logo" section, click the file input button
2. Select your logo image from your computer (any size!)
3. **Automatic compression happens:**
   - You'll see a "Compressing image..." notification
   - Image is optimized to max 200KB
   - Dimensions adjusted to max 400x400px
   - Quality maintained at 90%
4. Wait for the upload to complete
5. You'll see a success message showing:
   - Original file size
   - Compressed file size
   - Compression percentage
6. The logo preview will appear immediately

### Step 3: Update Branch Name (Optional)
1. In the "Branch Name" section, enter your desired name
2. Click the "Save" button
3. The name will update in the header immediately

### Step 4: Verify Changes
1. Navigate to any page on the website
2. Check the top-left corner of the header
3. Your custom logo and branch name should be displayed

## Technical Details

### Auto-Compression Features
- **Max File Size**: 200KB (automatically compressed)
- **Max Dimensions**: 400x400px (maintains aspect ratio)
- **Quality**: 90% (high quality maintained)
- **Format**: Automatically converted to PNG
- **Processing**: Uses Web Workers for fast compression
- **No Manual Work**: Everything happens automatically!

### Compression Benefits
1. **Faster Loading**: Smaller files load instantly
2. **Better Performance**: Optimized for web delivery
3. **No Quality Loss**: High-quality compression algorithm
4. **Bandwidth Savings**: Reduced data transfer
5. **SEO Friendly**: Fast-loading images improve rankings

### Storage
- Logos are stored in Supabase Storage bucket: `robotics_portal`
- Settings are saved in the `site_settings` table
- Logo URL is automatically generated and stored

### Display Logic
- If a logo is uploaded, it displays in the header
- If no logo is uploaded, a default CPU icon is shown
- Logo is responsive and works on all screen sizes
- Logo maintains aspect ratio with `object-contain`

### Validation
- File type validation (images only)
- Automatic compression before upload
- Clear success messages with compression stats
- Error handling for failed uploads

## Compression Examples

### Example 1: Large Photo
- **Original**: 2.5MB, 2000x2000px
- **Compressed**: 180KB, 400x400px
- **Reduction**: 92.8%
- **Quality**: Excellent

### Example 2: Medium Image
- **Original**: 800KB, 1200x1200px
- **Compressed**: 150KB, 400x400px
- **Reduction**: 81.3%
- **Quality**: Excellent

### Example 3: Small Logo
- **Original**: 150KB, 500x500px
- **Compressed**: 120KB, 400x400px
- **Reduction**: 20%
- **Quality**: Perfect

## Troubleshooting

### Logo Not Appearing
1. Check if the upload was successful (look for success message)
2. Refresh the page
3. Clear browser cache
4. Verify the image file is valid and not corrupted

### Upload Failed
1. Verify you're uploading an image file
2. Check your internet connection
3. Try a different image format
4. Check browser console for errors

### Compression Taking Too Long
1. Large files (>5MB) may take 5-10 seconds
2. Wait for the compression notification
3. Don't close the browser during upload
4. Check your internet speed

### Logo Looks Distorted
1. Use square images (1:1 aspect ratio) for best results
2. High-resolution images work best (they compress better)
3. Use PNG format with transparent background
4. Avoid extremely wide or tall images

## Best Practices

1. **Image Format**: Use PNG with transparent background for professional look
2. **Original Size**: Upload high-quality images (they compress better)
3. **Dimensions**: Square format works best (1:1 aspect ratio)
4. **Colors**: Ensure logo works well on both light and dark themes
5. **Simplicity**: Simple, clean logos work better at small sizes
6. **File Size**: Don't worry about size - compression is automatic!

## Example Workflow

```
1. Admin logs in → /admin
2. Clicks "Settings" tab
3. Uploads logo (e.g., university_logo.png - 3MB)
4. System compresses: 3MB → 180KB (94% reduction)
5. Success message shows compression stats
6. Updates branch name to "Robotics & AI Department"
7. Clicks Save
8. Logo appears in header across all pages
9. Fast loading on all devices!
```

## Compression Statistics Display

After successful upload, you'll see:
```
✓ Success
Logo uploaded successfully! 
Compressed from 2500.00KB to 180.50KB (92.8% reduction)
```

This shows:
- Original file size
- Compressed file size
- Percentage reduction
- Instant feedback on optimization

## Notes

- **No size limits**: Upload any size image, compression is automatic
- Logo changes are instant and don't require page reload
- Logo is visible to all website visitors
- Only admins can change the logo
- Previous logos are automatically replaced when uploading new ones
- Logo persists across sessions and browser refreshes
- Compression happens client-side (in your browser)
- High-quality compression algorithm maintains visual quality
- Web Workers ensure UI remains responsive during compression
