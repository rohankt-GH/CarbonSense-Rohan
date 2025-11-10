# CarbonSense 2.0 Design Guidelines

## Design Approach
**Reference-Based Approach**: Drawing inspiration from modern sustainability and productivity apps (Notion's clean data presentation + Linear's bold typography + eco-focused aesthetics)

## Core Design Principles
- **Environmental Focus**: Green-centric visual language emphasizing growth and sustainability
- **Data Clarity**: Clean presentation of metrics and statistics for easy comprehension
- **Engaging Gamification**: Visible progress indicators and achievement systems
- **Mobile-First Responsiveness**: Seamless experience across all devices

## Typography System
- **Primary Font**: Poppins for headings and emphasis
- **Secondary Font**: Inter for body text and data
- **Hierarchy**:
  - Hero/Page Titles: text-4xl to text-6xl, font-bold
  - Section Headers: text-2xl to text-3xl, font-semibold
  - Card Titles: text-xl, font-medium
  - Body Text: text-base, font-normal
  - Metrics/Stats: text-3xl to text-5xl, font-bold (tabular-nums)
  - Labels: text-sm, font-medium, uppercase tracking-wide

## Layout System
**Spacing Primitives**: Tailwind units of 4, 6, 8, 12, and 16 for consistent rhythm
- Section padding: py-12 (mobile), py-16 to py-20 (desktop)
- Card padding: p-6 (mobile), p-8 (desktop)
- Grid gaps: gap-4 (mobile), gap-6 to gap-8 (desktop)
- Container max-width: max-w-7xl with px-4 to px-8

## Page Layouts

### Navigation
Sticky top navbar with backdrop blur effect:
- Logo/Brand on left
- Icon-based navigation (Home, Dashboard, Map, Advisor, Profile) centered or right
- Current eco-points badge visible in navbar
- Mobile: Bottom navigation bar with icons

### Home/Landing Page
- **Hero Section** (80vh): Full-width with dynamic gradient background, large headline "Know Your Impact. Track It. Change It.", primary CTA button with backdrop blur, animated CO₂ reduction counter
- **Features Grid** (3 columns desktop, 1 mobile): Cards showcasing Carbon Tracking, AI Advisor, Smart Routes, each with Lucide icon, title, description
- **Impact Stats Section**: Large numbers showing community impact (total CO₂ saved, active users, eco-routes taken)
- **Social Proof**: Achievement showcase carousel with user testimonials
- **CTA Section**: Strong call-to-action to start tracking

### Dashboard (Carbon Footprint Tracker)
- **Stats Cards Grid** (2x2 on desktop, stacked mobile):
  - Energy Usage (⚡ icon, kWh value, trend indicator)
  - Water Consumption (💧 icon, Liters)
  - Travel Distance (🚗 icon, km)
  - CO₂ Emissions (🌫️ icon, kg, highlighted)
- **Carbon Calculator Form**: Clean form with labeled inputs, calculate button, result display with animation
- **Charts Section**: Full-width Recharts LineChart showing weekly/monthly trends
- **Recent Activities**: Timeline of eco-actions with points earned
- **Badge Display**: Current level (Bronze/Silver/Gold) with progress bar to next tier

### Smart Eco-Route Map
- **Map Container**: Full-height interactive Google Maps instance (min-height: 600px)
- **Route Search Panel**: Floating card overlay (top-left) with origin/destination inputs, transport mode selector
- **Route Comparison Cards**: Side-by-side floating cards showing:
  - Default Route: Distance, time, CO₂ emissions
  - Eco Route: Distance, time, CO₂ saved (highlighted in green)
- **Live GPS Toggle**: Button to center map on current location
- **Turn-by-turn Instructions**: Collapsible panel with step-by-step directions

### AI Sustainability Advisor
- **Chat Interface**: Full-height layout with message list area, input fixed at bottom
- **Message Bubbles**: User messages (right-aligned, green background), AI responses (left-aligned, white with border)
- **AI Recommendations Carousel**: Below chat, horizontal scroll of product/tip cards with images, titles, savings metrics
- **Quick Actions**: Suggested prompts as clickable chips

### Profile Page
- **Profile Header**: User avatar, name, location, member since date
- **Stats Overview**: Grid of achievements, total points, current level
- **Sustainability Preferences**: Editable cards for transport type, energy usage, goals
- **Leaderboard Section**: Top eco-warriors ranking table
- **Share Achievement**: Social sharing buttons for badges and stats

## Component Library

### Cards
- Rounded corners: rounded-xl
- Shadow: shadow-md, hover:shadow-lg transition
- Background: white with subtle border
- Padding: p-6 to p-8

### Buttons
- Primary CTA: Green background, white text, rounded-lg, px-6 py-3
- Secondary: White background, green border and text
- Icon Buttons: Circular, p-3, with hover state
- Buttons on images: backdrop-blur-md bg-white/20 (no additional hover/active states)

### Forms
- Input fields: rounded-lg border-2, focus:border-green-500, px-4 py-3
- Labels: text-sm font-medium mb-2
- Validation: Green checkmark or red error text

### Badges & Points
- Eco-points display: Pill shape, gradient background, bold number
- Level badges: Shield or medal icon with Bronze/Silver/Gold styling
- Achievement cards: Icon + title + description in grid

### Charts & Data Viz
- Recharts components with green color scheme
- Grid lines subtle gray
- Tooltip with white background, shadow
- Responsive aspect ratio

## Dynamic Backgrounds
- **Background System**: Gradient overlay that changes based on carbon footprint level
  - Low emissions: Vibrant green gradient (from-green-400 to-emerald-600)
  - Medium: Green to yellow gradient (from-green-400 to-yellow-500)
  - High: Yellow to orange warning gradient (from-yellow-400 to-orange-500)
- Applied to: Hero sections, dashboard header
- Animated transitions between states using Framer Motion

## Animations
- **Page Transitions**: Fade-in with Framer Motion (duration: 0.3s)
- **Card Entrance**: Staggered slide-up animation on scroll
- **Stat Counters**: Number counting animation when visible
- **Map Markers**: Bounce animation on placement
- **Achievement Unlocks**: Scale + confetti effect
- **Keep Minimal**: Focus on purposeful animations, avoid distraction

## Images
- **Hero Section**: Large sustainability-themed image (forest, wind turbines, solar panels, or green cityscape) as background with gradient overlay
- **Feature Cards**: Icon-based, no images needed
- **AI Product Recommendations**: Small product thumbnails (solar panel, showerhead, etc.) in carousel cards
- **Profile**: User avatar placeholder with eco-themed default icons

## Responsive Breakpoints
- Mobile: Base styles, single column
- Tablet (md:): 2-column grids, adjusted spacing
- Desktop (lg:): 3-4 column grids, full feature set, side-by-side layouts

## Footer
Simple centered footer with green accent: "Made with 💚 for a Sustainable Future" + social links