# Program Search Portal - Design Document

## Overview
The Program Search Portal is designed to help users search for programs, associated jobs, files, and ESP schedules with dedicated analysis features.

## UI/UX Layout

### Screen Layout Structure

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        PROGRAM SEARCH PORTAL                             │
├──────────────┬──────────────────────────────────────────────────────────┤
│              │                                                            │
│   LEFT PANE  │              MAIN CONTENT AREA                            │
│              │                                                            │
│ ┌──────────┐ │  ┌────────────────────────────────────────────────────┐  │
│ │Component │ │  │                                                    │  │
│ │Analysis  │ │  │   Search Bar                                       │  │
│ │  Button  │ │  │  ┌──────────────────────────────────────────────┐ │  │
│ │          │ │  │  │ 🔍 Enter Program/Job/File Name...       [🔎] │ │  │
│ │          │ │  │  └──────────────────────────────────────────────┘ │  │
│ │          │ │  │                                                    │  │
│ │ ┌──────┐ │ │  │  Results Section                                   │  │
│ │ │Click │ │ │  │  ┌─────────────────────────────────────────────┐  │  │
│ │ │Here  │ │ │  │  │ Filters: ☐ Programs  ☐ Jobs  ☐ Files       │  │  │
│ │ └──────┘ │ │  │  └─────────────────────────────────────────────┘  │  │
│ │          │ │  │                                                    │  │
│ └──────────┘ │  │  Results Table                                     │  │
│              │  │  ┌─────────────────────────────────────────────┐  │  │
│              │  │  │ Name      │ Type    │ Status  │ Action      │  │  │
│              │  │  ├─────────────────────────────────────────────┤  │  │
│              │  │  │ PROG_001  │ Program │ Active  │ View Details│  │  │
│ ┌──────────┐ │  │  ├─────────────────────────────────────────────┤  │  │
│ │   ESP    │ │  │  │ JOB_002   │ Job     │ Active  │ View Details│  │  │
│ │ Analysis │ │  │  ├─────────────────────────────────────────────┤  │  │
│ │  Button  │ │  │  │ FILE_003  │ File    │ Linked  │ View Details│  │  │
│ │          │ │  │  └─────────────────────────────────────────────┘  │  │
│ │          │ │  │                                                    │  │
│ │ ┌──────┐ │ │  │  Details Panel (On Selection)                     │  │
│ │ │Click │ │ │  │  ┌─────────────────────────────────────────────┐  │  │
│ │ │Here  │ │ │  │  │ Program: PROG_001                           │  │  │
│ │ └──────┘ │ │  │  │ Associated Jobs: 5                          │  │  │
│ │          │ │  │  │ Files Used: 12                              │  │  │
│ │          │ │  │  │ ESP Schedule: Running                       │  │  │
│ │          │ │  │  │ Last Updated: 2024-01-15                    │  │  │
│ │          │ │  │  └─────────────────────────────────────────────┘  │  │
│ └──────────┘ │  │                                                    │  │
│              │  └────────────────────────────────────────────────────┘  │
│              │                                                            │
└──────────────┴──────────────────────────────────────────────────────────┘
```

## Component Specifications

### 1. Left Navigation Pane
- **Width**: 200-250px
- **Background**: Light gray (#f5f5f5)
- **Components**:
  - **Component Analysis Button**
    - Purpose: Analyze relationships between programs, jobs, and files
    - Shows: Dependencies, data flow, file references
    - Color: Primary blue (#0066cc)
    
  - **ESP Analysis Button**
    - Purpose: View and analyze ESP (Extended Scheduling Protocol) schedules
    - Shows: Schedule timeline, run history, status
    - Color: Secondary purple (#6f42c1)

### 2. Main Content Area
- **Background**: White (#ffffff)
- **Padding**: 20px

#### Search Section
- **Search Bar**: 
  - Placeholder: "Enter Program/Job/File Name..."
  - Support for partial/fuzzy matching
  - Real-time suggestions dropdown
  - Icon: Search icon on left, clear button on right

#### Filters
- Checkboxes to filter results by type:
  - Programs
  - Jobs
  - Files
  - ESP Schedules

#### Results Table
- **Columns**:
  1. Name (sortable)
  2. Type (Program/Job/File/Schedule)
  3. Status (Active/Inactive/Running/Completed)
  4. Last Updated (sortable)
  5. Actions (View Details, Expand)

- **Row Features**:
  - Hover effect for better UX
  - Click to expand/view details
  - Color-coded type badges

#### Details Panel
- Displays when a result is selected
- Shows:
  - Item name and type
  - Associated items count
  - Files referenced
  - ESP schedule status
  - Metadata and timestamps

## Color Scheme
- **Primary**: #0066cc (Blue)
- **Secondary**: #6f42c1 (Purple)
- **Success**: #28a745 (Green)
- **Warning**: #ffc107 (Yellow)
- **Danger**: #dc3545 (Red)
- **Neutral**: #6c757d (Gray)

## Responsive Design
- **Desktop**: Full layout with all columns visible
- **Tablet**: Collapsible left pane, stacked details
- **Mobile**: Full-width search, stacked components

## User Interactions

### Search Flow
1. User enters search term in search bar
2. Real-time suggestions appear
3. User selects filter options (optional)
4. Results populate table
5. User clicks on row to view details
6. Details panel opens with full information

### Analysis Flows
- **Component Analysis**: Shows network graph of program→job→file relationships
- **ESP Analysis**: Shows timeline view of scheduled executions

## Key Features
✓ Full-text search across programs, jobs, files
✓ Filter by type and status
✓ Quick details panel on selection
✓ Component relationship analysis
✓ ESP schedule visualization
✓ Responsive design
✓ Export search results
✓ Save searches as favorites
