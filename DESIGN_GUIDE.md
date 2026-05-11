# TBM (The Book Mart) - Design Guide

## Design System Overview

TBM follows a **dense, information-rich, dark-mode-first UI** inspired by professional enterprise tools like Paperclip. The design emphasizes **keyboard navigation**, **text-centric visuals**, and **accessibility** for power users managing book inventory, sales, and operations.

---

## 1. Design Principles

### Core Principles
- **Dense but Scannable**: Maximum information visibility with strategic whitespace
- **Keyboard-First**: Global shortcuts for power users (Cmd+K, C, I, etc.)
- **Dark Mode Default**: Neutral grays (OKLCH color space) with accent colors for status/priority
- **Text-Centric**: Typography as primary visual element
- **Component-Driven**: Reusable, maintainable components with clear conventions

---

## 2. Color Palette

### Base Colors (OKLCH)
```
Primary Dark: #0f172a (slate-900)
Secondary Dark: #1e293b (slate-800)
Tertiary Dark: #334155 (slate-700)
Light Text: #f1f5f9 (slate-100)
Muted Text: #cbd5e1 (slate-400)
```

### Accent Colors (Status Indicators)
```
Success: #10b981 (emerald-500)
Warning: #f59e0b (amber-500)
Error: #ef4444 (red-500)
Info: #3b82f6 (blue-500)
```

### Semantic Colors
```
Border: #475569 (slate-600)
Hover BG: #1e293b (slate-800)
Selection BG: #334155 (slate-700)
```

---

## 3. Typography

### Font Stack
```
Primary Font: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif
Monospace: 'JetBrains Mono', 'Monaco', monospace
```

### Type Scale
```
H1 (Display): 32px, 1.2 line-height, 600 weight
H2 (Large Heading): 24px, 1.3 line-height, 600 weight
H3 (Medium Heading): 18px, 1.4 line-height, 600 weight
Body Large: 16px, 1.5 line-height, 400 weight
Body Normal: 14px, 1.5 line-height, 400 weight
Body Small: 12px, 1.4 line-height, 400 weight
Code: 13px, 1.4 line-height, 400 weight (monospace)
```

---

## 4. Component Library

### Buttons
- **Primary**: Emerald background, white text, 8px padding
- **Secondary**: Slate-700 background, slate-100 text
- **Ghost**: Transparent, slate-400 text, hover slate-300
- **Size variants**: sm (6px), md (8px), lg (12px)

### Input Fields
- **Background**: #1e293b (slate-800)
- **Border**: 1px solid #475569 (slate-600)
- **Focus**: Blue ring (#3b82f6)
- **Placeholder**: #64748b (slate-500)
- **Padding**: 8px 12px

### Cards
- **Background**: #1e293b (slate-800)
- **Border**: 1px solid #334155 (slate-700)
- **Padding**: 16px
- **Border Radius**: 6px
- **Box Shadow**: 0 4px 6px rgba(0, 0, 0, 0.3)

### Tables
- **Header Background**: #0f172a (slate-900)
- **Row Background**: #1e293b (slate-800)
- **Stripe Alternate**: #334155 (slate-700) every other row
- **Border**: 1px solid #334155 (slate-700)
- **Padding**: 12px 16px per cell

### Status Badges
- **Active**: Green background, white text
- **Inactive**: Gray background, muted text
- **Pending**: Amber background, dark text
- **Error**: Red background, white text

---

## 5. Layout System

### Spacing Scale
```
2px: 0.125rem
4px: 0.25rem
8px: 0.5rem
12px: 0.75rem
16px: 1rem
24px: 1.5rem
32px: 2rem
48px: 3rem
64px: 4rem
```

### Grid System
- **Container Width**: 1408px (1400px content + 4px padding)
- **Columns**: 12-column grid
- **Gap**: 16px
- **Responsive Breakpoints**: 640px, 768px, 1024px, 1280px

---

## 6. Key Interfaces

### Dashboard
- **High-level metrics** in card layout (books in stock, revenue, pending orders)
- **Real-time activity feed** with timestamps
- **Quick stats** visualization
- **Recently accessed items** section

### Inventory Management
- **Dense table** showing all books with:
  - ISBN, Title, Author
  - Stock count, Price, Status
  - Last Updated
- **Inline editing** (no modals)
- **Quick filters** in header

### Orders/Sales
- **Inbox-style interface** for customer orders
- **Priority-based sorting** (urgent, due today, upcoming)
- **Bulk actions** for processing multiple orders
- **Order details** in split-panel view

### Settings
- **Tabbed interface** for different settings categories
- **Form fields** with clear labels and helper text
- **Save/Cancel** buttons at bottom
- **Confirmation** for destructive actions

---

## 7. Keyboard Shortcuts

### Global Commands
```
Cmd+K (Ctrl+K)     : Open command palette
Cmd+/              : Show keyboard shortcuts help
Cmd+D              : Toggle dark/light mode
Escape             : Close modals/popups
```

### Dashboard
```
I                  : Go to Inventory
O                  : Go to Orders
S                  : Go to Sales Report
C                  : Create new book entry
```

### Inventory
```
/                  : Focus search
N                  : New book entry
E                  : Edit selected item
D                  : Delete selected item
Enter              : Open details
```

---

## 8. Accessibility Standards

- **WCAG 2.1 AA** compliant
- **Keyboard navigation** for all interactive elements
- **Screen reader** support (ARIA labels)
- **Color contrast** minimum 4.5:1 for text
- **Focus indicators** clearly visible (2px outline)

---

## 9. Animation Guidelines

### Transitions
- **Hover states**: 150ms ease-in-out
- **Fade in/out**: 200ms ease-in-out
- **Slide animations**: 300ms ease-out

### Principles
- Avoid excessive animations
- Keep UI responsive and snappy
- Use animations to guide attention, not distract

---

## 10. Responsive Design

### Mobile-First Approach
- **Desktop**: Full dashboard layout
- **Tablet (768px)**: Sidebar collapses, stacked cards
- **Mobile (640px)**: Single-column layout, bottom navigation
- **Touch targets**: Minimum 44px × 44px

---

## Implementation Tech Stack

- **Framework**: React 19 with TypeScript
- **Styling**: Tailwind CSS (CSS variables)
- **UI Primitives**: Radix UI
- **Pre-built Components**: shadcn/ui
- **Build Tool**: Vite
- **Package Manager**: pnpm

