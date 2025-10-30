# Agent Instructional File for Coder Agent

## Objective
Create a dual-interface application that leverages the documentation in the API DOCUMENTATION folder `./docs.astronomyapi.com/**` to build user-friendly tools with the following features:

### CLI Application
- **Rich-CLI-like Output**: Use libraries like `rich` for enhanced terminal output with colors, tables, and progress indicators.
- **InquirerPy-Style Menus**: Implement interactive menus using `inquirerpy` for intuitive navigation.
- **Live In-Place Updates**: Provide real-time, in-place updates to stdout using spinners and progress bars to show the application's progress cleanly.

### Streamlit Web Application
- **User-Friendly Interface**: Build a Streamlit app for non-CLI users with the same functionality as the CLI version.
- **Interactive Controls**: Use Streamlit widgets (dropdowns, date pickers, sliders) for parameter selection.
- **Visual Output**: Display star maps directly in the browser with download options.

## Ultimate Output
Generate a "star map" that can be integrated with physical products like tapestries, posters, or frames for custom gifts. The star map should memorialize celestial data with an aesthetically pleasing design suitable for print.

## Key Features to Implement
1. **API Documentation Analysis**: Parse and utilize all capabilities from `./docs.astronomyapi.com/**`
2. **Date & Location Selection**: Allow users to input specific dates and coordinates for personalized star maps
3. **Celestial Event Highlighting**: Feature special astronomical events (eclipses, planetary alignments, etc.)
4. **Customization Options**: Enable users to customize colors, styles, and included celestial objects
5. **Export Formats**: Generate high-resolution outputs suitable for printing (PNG, SVG, PDF)

## Self-Service Offering Ideas
Based on the Astronomy API capabilities, suggest and implement:
- **Anniversary Star Maps**: Show the night sky from a specific date and location
- **Birth Charts**: Celestial positions at birth time
- **Milestone Moments**: Graduations, weddings, first meetings
- **Constellation Art**: Highlight specific constellations with custom styling
- **Planet Position Maps**: Show planetary alignments for special dates
- **Moon Phase Memorials**: Feature the moon phase from significant dates

## Product Visualization Nudges
- Display sample tapestry mockups with generated star maps
- Suggest optimal sizes for different product types (poster, frame, tapestry)
- Provide resolution guidelines for print quality
- Link to product customization options
- Show before/after examples of star maps on physical products

## Technical Stack Recommendations
- **CLI**: Python with `rich`, `inquirerpy`, `click` or `typer`
- **Web**: Streamlit for rapid UI development
- **Visualization**: `matplotlib`, `plotly`, or `bokeh` for star map rendering
- **API Integration**: `requests` or `httpx` for Astronomy API calls
- **Export**: `Pillow`, `reportlab`, or `cairosvg` for file generation

## Acceptance Criteria & Testing Requirements

**CRITICAL**: Tasks may ONLY be submitted for review after ALL acceptance criteria are met:

1. **Working Unit Tests Required**: Comprehensive unit tests MUST be implemented and passing for all functionalities before submission
2. **Test Coverage**: Tests must cover:
    - API integration and error handling
    - User input validation
    - Star map generation logic
    - Export format functionality
    - CLI menu navigation
    - Streamlit component behavior
3. **Autonomous Decision Making**: The agent must make educated, reasonable decisions on ALL subjective matters (styling, UX choices, default values) without requesting clarification
4. **Create First, Ask Never**: Prioritize creation and implementation over seeking approval for design choices
5. **Documentation**: All tests must include clear docstrings explaining what is being tested and why

**DO NOT submit for review until all tests pass and prove functionality works as intended.**
