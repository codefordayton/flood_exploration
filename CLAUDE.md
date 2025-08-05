# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a flood risk visualization project for the Miami Conservancy District (MCD), focused on displaying dam information, flood risk areas, and real-time water data for the Dayton, Ohio region. The project consists of static HTML files that create interactive mapping dashboards.

## Architecture

### Core Files
- `index.html` - Main flood risk dashboard with interactive Leaflet map showing:
  - 5 MCD dams (Huffman, Germantown, Englewood, Lockington, Taylorsville) with status indicators
  - High-risk property areas (18,596 properties at 21% risk in Dayton)
  - FEMA floodplains (100-year and 500-year zones)
  - Storage basin areas
  - Layer controls and dam focus functionality

- `index2.html` - Live API demonstration showing integration with:
  - USGS Water Services API for real-time stream gauge data
  - FEMA National Flood Hazard Layer for official flood zones
  - Code examples for data integration

### Key Technical Components

**Mapping Technology:**
- Leaflet.js for interactive maps
- OpenStreetMap and Esri satellite base layers
- Layer groups for organized data display
- Custom markers and polygons for geographic features

**Data Sources Integration:**
- USGS Water Services API (station 03270500 - Great Miami River at Dayton)
- FEMA National Flood Hazard Layer WMS services
- Miami Conservancy District GeoPort data
- First Street Foundation climate risk projections

**UI Components:**
- Responsive sidebar with dam controls and layer toggles
- Status indicators (normal/elevated/high risk levels)
- Interactive legend and data source attribution
- Mobile-responsive design with CSS Grid

## Development Commands

This is a static HTML project with no build system. Development workflow:

1. **Local Development:** Open HTML files directly in browser or use a simple HTTP server:
   ```bash
   python -m http.server 8000
   # or
   npx serve .
   ```

2. **No build, test, or lint commands** - this is pure HTML/CSS/JavaScript

## Key Data and Context

**Critical Infrastructure Alert:**
- 18,596 properties downstream of Huffman Dam at risk
- 21% of downstream properties face flood risk in next 30 years
- $140M funding gap for necessary dam repairs
- April 2025 event was 12th largest in MCD history (22.5 billion gallons peak storage)

**Dam Status Monitoring:**
- Huffman Dam: CRITICAL status, upstream walls need repair
- Taylorsville Dam: HIGH risk status  
- Germantown & Englewood: ELEVATED status
- Lockington Dam: NORMAL status

**Geographic Focus:**
- Centered on Dayton, Ohio area (39.7589, -84.1916)
- Great Miami River basin coverage
- Historical context: 228% increase in storage capacity over 80 years since 1913 flood

## API Integration Notes

When working with the live data integration (index2.html):

- USGS API may have CORS restrictions in browser - implement server-side proxy for production
- FEMA WMS services require proper layer naming and CRS configuration
- Station 03270500 monitors conditions near Huffman Dam
- Flood stage threshold: 41 feet for risk assessment
- Historical data available back to 1922 for trend analysis

## Styling and UI Patterns

- Uses CSS Grid for responsive layouts
- Gradient backgrounds and glassmorphism effects
- Status indicators with color coding (green/yellow/red)
- Toggle switches for layer controls
- Card-based information display
- Professional typography with Segoe UI font stack