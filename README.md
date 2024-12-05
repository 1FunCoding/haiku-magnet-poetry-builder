# Interactive Haiku Magnet Poetry Builder
<img width="1257" alt="image" src="https://github.com/user-attachments/assets/35385064-fccc-4a65-a2a9-15d0053319cb">
<img width="1257" alt="image" src="https://github.com/user-attachments/assets/26e6c1b4-dbac-4fa9-9f91-8f1eafe16fad">


## Overview
The Interactive Haiku Magnet Poetry Builder is an interactive web application that allows users to create a haiku by dragging and dropping words onto a syllable grid. Users can navigate through different sets of words using previous and next buttons, simulating a magnetic poetry experience.

## Project Files
The project consists of several key components:

- **index.html**: Defines the structure of the page, including the haiku syllable grid, buttons for navigation, and script inclusion.
- **index.css**: Styles the haiku syllable grid, magnets, and buttons, ensuring a visually appealing interface.
- **fetch.js**: Implements a monkey-patched `fetch` function to simulate server responses on the client side.
- **index.js**: Implements the logic for loading magnets, handling user interaction, and managing drag-and-drop functionality.
- **react.css**: Provides typographic improvements, better media handling, and default form and button styles for the entire page.

## Part 1: Client-Side Fetch Implementation
The project begins by simulating server functionality on the client side using a custom implementation of the `fetch` function:

1. **Monkey Patching Fetch**:
   - Created a new function called `fetch` in `fetch.js`.
   - Implemented a function called `response` inside the `fetch` function, which simulates HTTP responses based on the status code and payload.
   - Added error handling to check for incorrect URL paths or non-GET requests.

2. **Word Retrieval**:
   - Implemented logic to parse the URL search parameters for `offset` and `count`.
   - Words are retrieved from a simulated server response, sliced according to the `offset` and `count` values.
   - If `count` exceeds 100, a "Bad Request" response is returned.

3. **Integrating Fetch with Magnets**:
   - Used the custom `fetch` function in `index.js` to load word magnets.
   - Created an initial fetch call to load a default set of words (`offset = 0`, `count = 10`).
   - Implemented previous and next buttons to navigate through sets of words, clearing the existing words before adding the new set.

## Part 2: Drag and Drop Functionality
The magnets can be dragged and dropped onto predefined dots, enabling users to create their haiku interactively:

1. **Word Magnets**:
   - In `index.js`, each word is represented as an element, styled as a "magnet" and made draggable.
   - Words are loaded using the `createMagnet` function, which applies CSS styling and makes them movable.

2. **Dot Elements**:
   - Dots are created in the `index.html` as `<li>` elements inside multiple `<ul>` lists representing the haiku syllable structure (5-7-5 syllables).

3. **Event Handling**:
   - Drag-and-drop functionality is implemented to allow users to place words on specific syllable dots.
   - Added CSS classes (`.available`, `.unavailable`) to represent the state of each drop target, ensuring that words are only placed in valid spots.

## Styling

## Developer Information
- **Developer**: Jerry Wang (qwang7@scu.edu)
The project utilizes **index.css** and **react.css** for its styling:

- **index.css** styles the main elements on the page:
  - The `body` is styled to ensure that all elements are centered.
  - The `.magnet` class styles word elements as draggable magnets with rounded corners and shadows for better visibility.
  - Buttons (`#previous`, `#next`) are styled for better interaction, including hover effects and disabled states.
- **react.css** serves as a reset and base styling file to improve accessibility, typography, and media handling consistency across different browsers.

## How to Run
1. Ensure all project files are in the same directory.
2. Open `index.html` in your browser to launch the Interactive Haiku Magnet Poetry Builder.
3. Use the "Previous" and "Next" buttons to navigate through word sets.
4. Drag and drop word magnets onto the syllable dots to create your haiku.




