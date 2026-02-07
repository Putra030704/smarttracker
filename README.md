# 📦 SmartTrack - Modern Tracking System

A production-ready, full-stack smart tracking system built with Next.js 16, featuring a beautiful 2026-style design with glassmorphism, smooth animations, and real-time updates.

## ✨ Features

### 🎨 Modern UI/UX (2026 Style)
- **Glassmorphism Design** - Beautiful frosted glass cards with blur effects
- **Soft Gradients** - Modern color schemes with neon accents
- **Framer Motion Animations** - Smooth transitions and micro-interactions
- **Responsive Design** - Mobile-first approach with Tailwind CSS
- **Dark Mode Support** - Seamless light/dark theme switching

### 📊 Core Functionality
- **Landing Page** - Clean tracking code input with animated submit button
- **Tracking Detail Page** - Dynamic routes (`/track/[unique_code]`)
- **Real-time Updates** - Auto-refresh every 30 seconds
- **QR Code Generation** - Automatic QR codes for each tracking record
- **Timeline History** - Animated tracking progress timeline
- **Progress Indicators** - Visual progress bars with animations
- **Loading Skeletons** - Beautiful loading states
- **Error Handling** - Graceful error states with user-friendly messages

### 🔒 Security Features
- **Rate Limiting** - API rate limiting (60 req/min for public, 30 req/min for admin)
- **Input Sanitization** - All inputs are sanitized and validated
- **No Public Data Endpoints** - Query only by unique code
- **Secure API Routes** - Protected Next.js API routes

### 🛠️ Admin Dashboard
- **Animated Data Tables** - Beautiful tables with hover effects
- **Inline Editing** - Edit tracking records directly in the table
- **CRUD Operations** - Create, Read, Update, Delete tracking records
- **Search & Filter** - Quick search by code, name, or service type
- **Pagination** - Efficient data pagination
- **Statistics Cards** - Overview cards with animated counters
- **Bulk Actions** - Delete multiple records

### 🗄️ Database
- **Prisma ORM** - Type-safe database operations
- **SQLite** - Lightweight, file-based database
- **Tracking History** - Complete audit trail of all status changes
- **QR Code Storage** - Base64 encoded QR codes in database

## 🚀 Technology Stack

### Core Framework
- **Next.js 16** - React framework with App Router
- **TypeScript 5** - Type-safe development
- **React 19** - Latest React features

### Styling & UI
- **Tailwind CSS 4** - Utility-first CSS
- **shadcn/ui** - High-quality component library
- **Framer Motion** - Animation library
- **Lucide React** - Icon library
- **next-themes** - Theme management

### Backend & Database
- **Prisma ORM** - Database toolkit
- **SQLite** - Database engine
- **Next.js API Routes** - Server-side logic
- **QRCode** - QR code generation

### Utilities
- **Zod** - Schema validation
- **date-fns** - Date manipulation
- **clsx & tailwind-merge** - Class utilities

## 📦 Sample Data

The system comes pre-seeded with 5 sample tracking records:

| Tracking Code | Owner Name | Service Type | Status | Stage |
|--------------|------------|--------------|--------|-------|
| A1B2C3D4 | John Doe | Express | In Transit | In Transit |
| E5F6G7H8 | Jane Smith | Standard | Processing | Processing |
| I9J0K1L2 | Michael Johnson | International | Delivered | Delivered |
| M3N4O5P6 | Sarah Williams | Same Day | Pending | Order Received |
| Q7R8S9T0 | David Brown | Economy | Delayed | In Transit |

## 🚀 Quick Start

```bash
# Install dependencies
bun install

# Setup database
bun run db:push

# Seed database with sample data
bun run db:seed

# Start development server
bun run dev
```

Visit the Preview Panel to see your application running!

## 📁 Project Structure

```
src/
├── app/
│   ├── page.tsx                    # Landing page
│   ├── layout.tsx                  # Root layout
│   ├── globals.css                 # Global styles
│   ├── track/
│   │   └── [unique_code]/
│   │       └── page.tsx           # Tracking detail page
│   ├── admin/
│   │   └── page.tsx               # Admin dashboard
│   └── api/
│       ├── tracking/
│       │   └── [unique_code]/
│       │       └── route.ts       # GET tracking by code
│       └── admin/
│           └── tracking/
│               ├── route.ts       # GET/POST trackings
│               └── [id]/
│                   └── route.ts   # PUT/DELETE tracking
├── components/
│   └── ui/                        # shadcn/ui components
├── hooks/
│   └── use-toast.ts               # Toast hook
└── lib/
    ├── db.ts                      # Prisma client
    └── utils.ts                   # Utility functions
prisma/
├── schema.prisma                  # Database schema
└── seed.ts                       # Database seeder
```

## 🎯 User Flows

### 1. Track a Package
1. Visit the landing page
2. Enter a tracking code (e.g., `A1B2C3D4`)
3. Click "Track Now" or press Enter
4. View detailed tracking information with animated cards

### 2. Access Tracking Directly
1. Navigate to `/track/[unique_code]`
2. System automatically loads and displays tracking data
3. View real-time status, progress, and history

### 3. Admin Dashboard
1. Navigate to `/admin`
2. View all tracking records in animated table
3. Create new tracking records
4. Edit records inline
5. Search and filter
6. Delete records

## 🎨 Visual Features

### Glassmorphism Cards
```tsx
<div className="bg-white/70 dark:bg-slate-800/70 backdrop-blur-xl border border-slate-200/50 dark:border-slate-700/50 rounded-2xl shadow-xl">
  {/* Content */}
</div>
```

### Animated Gradients
```tsx
<div className="bg-gradient-to-r from-violet-600 to-cyan-600">
  {/* Content */}
</div>
```

### Framer Motion Animations
```tsx
<motion.div
  initial={{ opacity: 0, y: 20 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ type: 'spring', stiffness: 100, damping: 15 }}
>
  {/* Content */}
</motion.div>
```

### Status Colors
- **Pending** - Yellow/Orange gradient
- **Processing** - Purple/Violet gradient
- **In Transit** - Blue/Cyan gradient
- **Delivered** - Green/Emerald gradient
- **Delayed** - Red/Pink gradient

## 🔧 API Endpoints

### Public API
- `GET /api/tracking/[unique_code]` - Get tracking by code

### Admin API
- `GET /api/admin/tracking` - List all trackings (with pagination)
- `POST /api/admin/tracking` - Create new tracking
- `PUT /api/admin/tracking/[id]` - Update tracking
- `DELETE /api/admin/tracking/[id]` - Delete tracking

## 🔐 Security Implementation

### Rate Limiting
- Public endpoints: 60 requests per minute
- Admin endpoints: 30 requests per minute
- Per-IP tracking with in-memory storage

### Input Validation
```typescript
function sanitizeInput(input: string): string {
  return input
    .trim()
    .replace(/[<>]/g, '')  // Remove HTML tags
    .substring(0, 100)     // Limit length
}
```

### Secure Database Queries
- All queries use Prisma ORM
- Parameterized queries prevent SQL injection
- Query only by unique code (no list endpoints)

## 📊 Database Schema

### Tracking Model
```prisma
model Tracking {
  id          String   @id @default(cuid())
  uniqueCode  String   @unique
  name        String
  serviceType String
  status      String
  stage       String
  lastUpdated DateTime @updatedAt
  notes       String?
  qrCode      String?
  createdAt   DateTime @default(now())
  history     TrackingHistory[]
}
```

### TrackingHistory Model
```prisma
model TrackingHistory {
  id         String   @id @default(cuid())
  trackingId String
  tracking   Tracking @relation(fields: [trackingId], references: [id])
  status     String
  stage      String
  notes      String?
  timestamp  DateTime @default(now())
}
```

## 🎯 Status & Stage Options

### Status Options
- `pending` - Order received, awaiting processing
- `processing` - Being prepared
- `in-transit` - On the way
- `delivered` - Successfully delivered
- `delayed` - Delivery delayed

### Stage Options
- `order-received` - Order confirmed
- `processing` - Processing package
- `in-transit` - In transportation
- `out-for-delivery` - With delivery agent
- `delivered` - Delivered successfully

### Service Type Options
- `Express` - Fast delivery
- `Standard` - Regular delivery
- `Economy` - Budget delivery
- `Same Day` - Same-day delivery
- `International` - International shipping

## 🚀 Production Deployment

### Build
```bash
bun run build
```

### Environment Variables
Create `.env` file:
```env
DATABASE_URL="file:./db/custom.db"
NEXT_PUBLIC_BASE_URL="https://yourdomain.com"
```

### Start Production Server
```bash
bun start
```

## 📱 Responsive Breakpoints

- **Mobile**: < 640px (sm)
- **Tablet**: 640px - 1024px (md, lg)
- **Desktop**: > 1024px (xl, 2xl)

## 🎨 Customization

### Update Colors
Edit `src/app/globals.css` to modify the color scheme:

```css
:root {
  --primary: oklch(0.205 0 0);
  /* ... other colors */
}
```

### Modify Animations
Adjust Framer Motion props in component files:

```tsx
<motion.div
  initial={{ y: 20, opacity: 0 }}
  animate={{ y: 0, opacity: 1 }}
  transition={{ duration: 0.5, ease: 'easeOut' }}
>
```

## 🐛 Troubleshooting

### Database Issues
```bash
# Reset database
bun run db:reset

# Re-seed data
bun run db:seed
```

### Build Errors
```bash
# Clear Next.js cache
rm -rf .next

# Reinstall dependencies
rm -rf node_modules bun.lockb
bun install
```

## 📄 License

This project is built with ❤️ using modern web technologies.

## 🙏 Acknowledgments

- **Next.js** - The React framework
- **shadcn/ui** - Beautiful UI components
- **Framer Motion** - Smooth animations
- **Prisma** - Type-safe database toolkit
- **Tailwind CSS** - Utility-first CSS framework

---

Built with modern 2026 design principles for the best user experience! 🚀✨
