# 📦 Sample Tracking Codes

Use these codes to test the Smart Tracking System:

## Quick Test Codes

| Code | Owner | Service | Status | Stage |
|------|-------|---------|--------|-------|
| `A1B2C3D4` | John Doe | Express | In Transit | In Transit |
| `E5F6G7H8` | Jane Smith | Standard | Processing | Processing |
| `I9J0K1L2` | Michael Johnson | International | Delivered | Delivered |
| `M3N4O5P6` | Sarah Williams | Same Day | Pending | Order Received |
| `Q7R8S9T0` | David Brown | Economy | Delayed | In Transit |

## How to Test

### 1. From Landing Page
1. Enter any code from the table above
2. Click "Track Now" or press Enter
3. View the tracking details

### 2. Direct URL Access
Navigate directly to:
- `/track/A1B2C3D4` - View in-transit package
- `/track/E5F6G7H8` - View processing package
- `/track/I9J0K1L2` - View delivered package
- `/track/M3N4O5P6` - View pending package
- `/track/Q7R8S9T0` - View delayed package

### 3. Admin Dashboard
1. Go to `/admin`
2. View all tracking records
3. Create, edit, or delete records
4. Search and filter

## Test Scenarios

### ✅ Successful Tracking
- Try: `A1B2C3D4`
- Expected: Shows detailed tracking info with timeline

### ❌ Invalid Code
- Try: `INVALID123`
- Expected: Shows "Tracking Not Found" error

### 🔄 Real-time Updates
- Open a tracking page
- Wait 30 seconds
- Page auto-refreshes with latest data

### 📱 QR Code
- Any tracking page shows a QR code
- Scan to view tracking on mobile

## Admin Features

### Create New Tracking
1. Go to `/admin`
2. Click "New Tracking"
3. Fill in details
4. Click "Create Tracking"

### Edit Tracking
1. Click edit icon (pencil) on any row
2. Modify fields inline
3. Click save icon

### Delete Tracking
1. Click more options (three dots)
2. Select "Delete"
3. Confirm deletion

## Tips

- Use the search bar to find specific trackings
- Click on tracking codes to view details
- Hover over table rows for quick actions
- Use pagination to navigate through records

---

All sample data is auto-generated for testing purposes! 🚀
