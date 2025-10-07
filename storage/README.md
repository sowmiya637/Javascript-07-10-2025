# Theme Selector Demo

## Overview
This demonstrates how to store and manage user-selected **theme colors** using:

- **localStorage** → Permanent storage (even after closing browser)
- **sessionStorage** → Temporary storage (only for the current tab session)
- **Cookies** → Can have expiration dates and sent to server

Users can select a theme color, and the selection will persist based on the storage type used.

---

## Features

1. **Set Theme Color**
   - Users can choose **Light Blue, Light Green, or Light Pink**.
   - The selected color is applied immediately to the page background.

2. **Persist Theme**
   - **localStorage** → Saves theme permanently.
   - **sessionStorage** → Saves theme only for the current browser tab.
   - **Cookies** → Saves theme for 1 day.

3. **Reset Theme**
   - Clears all storage values.
   - Resets the background color to white.

4. **Display Storage Info**
   - Shows current values of `localStorage`, `sessionStorage`, and cookie for the theme.


