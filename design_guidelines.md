# PortTrade Vision - Design Guidelines

## Design Approach

**Selected System:** Carbon Design System (IBM)  
**Rationale:** Purpose-built for data-intensive enterprise applications with excellent support for dashboards, tables, and data visualization. Aligns perfectly with HPCL's professional B2B context.

## Typography System

**Font Stack:** IBM Plex Sans via Google Fonts CDN
- **Headings:** 
  - H1: 2.5rem (40px), font-semibold
  - H2: 2rem (32px), font-semibold  
  - H3: 1.5rem (24px), font-medium
  - H4: 1.25rem (20px), font-medium
- **Body:** 1rem (16px), font-normal, leading-relaxed
- **Small/Caption:** 0.875rem (14px), font-normal
- **Data/Metrics:** IBM Plex Mono for numbers and data points, font-medium

## Layout & Spacing System

**Tailwind Units:** Consistently use 4, 6, 8, 12, 16, 24 for spacing (p-4, m-6, gap-8, etc.)

**Grid Structure:**
- Container: max-w-7xl mx-auto px-6
- Dashboard cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6
- Data tables: Full-width with responsive horizontal scroll
- Two-column layouts: grid-cols-1 lg:grid-cols-3 (2:1 ratio for main/sidebar)

## Page-Specific Layouts

### Public Landing Page
**No Hero Image** - Data-first approach with immediate value
- **Above fold:** Company logo/nav + headline + 3 KPI stat cards in grid-cols-3
- **Quick insights section:** 2-column layout with bar chart (imports) and line chart (exports trend)
- **Trust section:** Partner logos grid + brief capability statements
- **CTA section:** Centered call-to-action with login button
- **Footer:** Comprehensive with navigation links, contact info, compliance statements

### Login Page
- **Layout:** Centered card (max-w-md) on clean background
- **Elements:** Logo, form fields (email, password), primary button, "Forgot password?" link
- **Form spacing:** gap-6 between input groups, p-8 card padding

### Dashboard (Post-Login)
**Header:** Logo, navigation tabs (Dashboard | Query | Upload), user menu, logout
**KPI Cards:** 4-column grid (Total Imports, Total Exports, Active Ports, Top Products)
- Card structure: Icon + Label + Large number + Trend indicator (↑/↓ percentage)
- Padding: p-6, shadow-md, rounded-lg

**Charts Section:** 2-column grid
- Left: Stacked bar chart (Import/Export by Month)
- Right: Pie chart (Top Products Distribution)
- Chart container: p-6, min-height 400px

**Recent Transactions Table:** Full-width below charts
- Columns: Date, Port, Product, Type (Import/Export), Quantity, Value
- Pagination: Bottom-right, 10 rows per page
- Spacing: py-4 for rows, px-6 for cells

### Query Page
**Filter Panel:** Left sidebar (w-80), sticky positioning
- Date range picker (Days/Weeks/Months/Custom tabs)
- Port multi-select dropdown
- Product multi-select dropdown  
- Type toggle (Import/Export/Both)
- Apply button at bottom

**Results Area:** Main content (flex-1)
- Results summary header: "Showing X results for [criteria]"
- Tabbed view: Table view | Chart view
- Export button (Download CSV) top-right

### CSV Upload Page
**Two-column layout:**
- Left (2/3): Drop zone for file upload + preview table
- Right (1/3): Column mapping interface (Source → Destination)
- Upload button and progress bar at bottom
- Success/error notifications using toast patterns

### Chatbot Interface
**Fixed position:** Bottom-right corner, z-50
- Collapsed: Circular button (w-14 h-14) with chat icon
- Expanded: Card (w-96 h-[500px]) with header, message area, input
- Message bubbles: User (right-aligned), Bot (left-aligned), gap-4 between messages
- Input area: Sticky bottom, p-4, with send icon button

## Component Library

**Buttons:**
- Primary: px-6 py-3, rounded-md, font-medium, shadow-sm
- Secondary: px-6 py-3, rounded-md, font-medium, border-2
- Icon buttons: p-2, rounded-full

**Cards:**
- Standard: p-6, rounded-lg, shadow-md
- Stat cards: p-6, rounded-lg, shadow-sm, border-l-4 (accent border)

**Form Inputs:**
- Text/Select: px-4 py-2.5, rounded-md, border, w-full
- Labels: mb-2, font-medium, text-sm
- Error states: border-red-500, text-red-600 helper text

**Tables:**
- Header: Sticky, font-semibold, border-b-2, py-4
- Rows: border-b, py-3, hover states
- Alternating row treatment for readability

**Navigation:**
- Top nav: h-16, flex items-center, border-b, px-6
- Tabs: Horizontal with active indicator (border-b-2)

**Data Visualization:**
- Use Recharts library via CDN
- Chart containers: min-h-[300px], p-6
- Legend placement: bottom-center
- Responsive: Full-width on mobile, multi-column on desktop

## Icons
**Library:** Heroicons via CDN (outline for nav, solid for actions)
- Navigation: 24px (w-6 h-6)
- Buttons: 20px (w-5 h-5)
- KPI cards: 32px (w-8 h-8)

## Accessibility
- All form inputs have associated labels
- Focus states: ring-2 ring-offset-2 on interactive elements
- ARIA labels for icon-only buttons
- Keyboard navigation support for all interactive components
- Sufficient contrast ratios for all text (WCAG AA)

## Animations
**Minimal, purposeful only:**
- Hover transitions: transition-colors duration-200
- Chart loading: Simple fade-in
- Chatbot expand/collapse: transition-all duration-300
- No scroll animations or parallax effects

**Key Principle:** Professional, data-centric enterprise interface prioritizing clarity, efficiency, and trust over visual flair.