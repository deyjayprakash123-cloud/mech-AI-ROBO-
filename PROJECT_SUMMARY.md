# Mechanical (Robotics/AI) Branch Portal - Project Summary

## Overview
A comprehensive, futuristic portal website for the Mechanical Engineering (Robotics/AI) Branch featuring a full-featured admin panel, dynamic content management, and stunning visual design.

## Key Features Implemented

### 🎨 Design & User Experience
- **Futuristic Theme**: Dark background (deep blue/black) with cyan/neon blue glowing accents
- **Animated Elements**: Floating icons, pulse effects, smooth transitions, and animated counters
- **Responsive Design**: Desktop-first approach with mobile adaptation
- **Custom Utilities**: Gradient text, glow effects, tech borders, and grid patterns

### 📄 Public Pages
1. **Home Page**
   - Hero section with animated floating icons (CPU, Brain, Cog)
   - Animated counters displaying key metrics (labs, projects, students, papers)
   - Latest news showcase
   - Call-to-action sections

2. **About Us**
   - History, Vision, and Mission sections
   - Department head's message
   - Dynamic content from database

3. **Academics**
   - Core courses with icons
   - Laboratory facilities information
   - Curriculum details

4. **Achievements**
   - Categorized achievement cards
   - Image support
   - Date-based sorting

5. **News & Announcements**
   - Published news articles
   - Category and tag filtering
   - Excerpt and full content support

6. **Students**
   - Student organizations
   - Upcoming events
   - Activity highlights

7. **Alumni Directory**
   - Searchable alumni profiles
   - Graduation year, company, industry information
   - LinkedIn integration
   - Approval system

8. **Gallery**
   - Album-based organization
   - Photo viewer with captions
   - Modal image preview

9. **Contact**
   - Contact form with validation
   - Google Maps integration
   - Contact information display

### 🔐 Authentication System
- Username/password authentication
- First user automatically becomes admin
- Secure session management
- Role-based access control

### 🛠️ Admin Panel
Comprehensive content management system with tabs for:

1. **News Management**
   - Create, edit, delete news articles
   - Publish/unpublish toggle
   - Category and tag management
   - Image upload support

2. **Achievements Management**
   - Add/remove achievements
   - Category organization
   - Date tracking

3. **Alumni Management**
   - Approve/reject alumni submissions
   - Edit alumni profiles
   - Delete profiles

4. **Gallery Management**
   - Create/delete albums
   - Upload photos with captions
   - Album cover images

5. **Contact Submissions**
   - View all contact form submissions
   - Mark as read/unread
   - Delete submissions

6. **Settings**
   - Homepage statistics configuration
   - Contact information management
   - About content editing

### 💾 Database Schema
**Tables:**
- `profiles` - User profiles with roles
- `news` - News articles with publishing status
- `achievements` - Achievement records
- `alumni` - Alumni directory with approval system
- `gallery_albums` - Photo album organization
- `gallery_photos` - Individual photos
- `contact_submissions` - Contact form entries
- `site_settings` - Configurable site settings

**Storage Buckets:**
- `app-806xhw354ao1_images` - Image uploads
- `app-806xhw354ao1_documents` - PDF and document uploads

### 🔒 Security Features
- Row Level Security (RLS) enabled on all tables
- Admin-only access to management functions
- Public read access for published content
- Secure file upload policies

## Technology Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for build tooling
- **React Router** for navigation
- **Tailwind CSS** for styling
- **shadcn/ui** for UI components
- **Lucide React** for icons

### Backend
- **Supabase** for database and authentication
- **PostgreSQL** for data storage
- **Supabase Storage** for file management

### Key Libraries
- `@supabase/supabase-js` - Database client
- `react-hook-form` - Form management
- `zod` - Schema validation
- `sonner` - Toast notifications

## Project Structure
```
src/
├── components/
│   ├── common/
│   │   ├── AnimatedCounter.tsx
│   │   ├── Header.tsx
│   │   └── Footer.tsx
│   └── ui/ (shadcn components)
├── db/
│   ├── supabase.ts
│   └── api.ts
├── hooks/
│   ├── use-auth.tsx
│   └── use-toast.tsx
├── pages/
│   ├── Home.tsx
│   ├── About.tsx
│   ├── Academics.tsx
│   ├── Achievements.tsx
│   ├── News.tsx
│   ├── Students.tsx
│   ├── Alumni.tsx
│   ├── Gallery.tsx
│   ├── Contact.tsx
│   ├── Login.tsx
│   └── Admin.tsx
├── types/
│   └── index.ts
├── App.tsx
├── routes.tsx
└── index.css
```

## Getting Started

### First Time Setup
1. The first user to register will automatically become an admin
2. Log in with your credentials
3. Access the Admin Panel to start adding content

### Admin Panel Access
- Navigate to `/login`
- Sign up with a username and password
- After registration, you'll have admin access
- Go to `/admin` to manage content

### Content Management
All content can be managed through the admin panel:
- **News**: Create articles, set categories, publish/unpublish
- **Achievements**: Add accomplishments with dates and categories
- **Alumni**: Approve submitted profiles, manage directory
- **Gallery**: Create albums and upload photos
- **Contacts**: View and manage contact form submissions

## Design System

### Color Palette
- **Background**: `hsl(222 47% 11%)` - Deep blue-black
- **Primary**: `hsl(189 94% 43%)` - Cyan
- **Primary Glow**: `hsl(189 94% 63%)` - Light cyan
- **Secondary**: `hsl(217 91% 60%)` - Blue
- **Muted**: `hsl(217 33% 17%)` - Dark gray-blue

### Custom Utilities
- `.gradient-text` - Gradient text effect
- `.glow-effect` - Box shadow glow
- `.glow-text` - Text shadow glow
- `.tech-border` - Futuristic border style
- `.grid-pattern` - Background grid pattern
- `.animate-float` - Floating animation
- `.animate-pulse-glow` - Pulsing glow animation

## Features Highlights

### Animations
- Floating icons on homepage
- Animated counters with easing
- Smooth page transitions
- Hover glow effects
- Pulse animations

### Responsive Design
- Desktop-first approach
- Mobile-friendly navigation
- Adaptive layouts
- Touch-friendly interfaces

### Performance
- Optimized database queries
- Lazy loading for images
- Efficient state management
- Fast page loads

## Database Initial Data
The system includes default settings for:
- Homepage statistics (labs, projects, students, papers)
- Contact information
- About content (history, vision, mission)

## Security Notes
- All sensitive operations require admin authentication
- Public users can view published content
- Alumni can submit profiles for approval
- Contact forms are accessible to all visitors

## Future Enhancements
Potential areas for expansion:
- Rich text editor for news content
- Bulk image upload for gallery
- Advanced search and filtering
- Email notifications for contact submissions
- Analytics dashboard
- PDF document management for academics section
- Event calendar integration

## Support
For questions or issues:
- Check the admin panel for content management
- Review the database schema in migrations
- Consult the API documentation in `src/db/api.ts`

---

**Built with modern web technologies for a cutting-edge user experience.**
