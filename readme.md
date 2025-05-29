# Interactive SDG Circle Graph Generator

This web-based tool allows you to create and customize an interactive circular graph inspired by the UN's Sustainable Development Goals (SDGs). Each of the 17 SDG segments has a height determined by a user-defined value, visualized extending from a central baseline.

**Live Demo:** (You would host this on GitHub Pages or similar and link it here)
_e.g., `https://thiruisme.github.io/sdgradialchart/`_

## Features

*   **Interactive Visualization:** 17 segments representing the SDGs, with heights dynamically changing based on input values.
*   **Custom Value Range:** Define a minimum and maximum value for the data, and the graph will scale accordingly.
*   **Multiple Input Methods:**
    *   **Sliders:** Intuitive range sliders for each SDG.
    *   **Number Inputs:** Manually type in precise values for each SDG.
    *   **CSV Upload:** Load data for all 17 SDGs from a CSV file.
*   **Dynamic Labels:**
    *   "SDG #" labels are positioned along a guide circle, following its curvature for a clean look.
    *   The current value for each segment is displayed within the segment itself (if space permits).
*   **SVG Export:** Download the generated chart as a Scalable Vector Graphic (SVG) file for high-quality use in reports, presentations, or further editing.
*   **Responsive Design:** Controls and graph layout adjust for different screen sizes.

## How to Use

1.  **Open the `index.html` (or the hosted page) in a web browser.**
2.  **Set Value Range (Optional):**
    *   In the "Chart Controls" panel, go to the "Value Range" section.
    *   Enter your desired **Min** and **Max** values.
    *   Click **"Apply Range"**. The sliders and number inputs will update to this new range. The default range is 0-16.
3.  **Input Data:**
    *   **Manually:**
        *   Use the sliders under "SDG Values" to adjust the value for each goal.
        *   Alternatively, type a number directly into the input field next to each slider. The slider and number input are synced.
    *   **Via CSV Upload:**
        *   Prepare a CSV file with your data. Two formats are supported:
            1.  **Simple Format:** 17 lines, each with a single numeric value. The first line is for SDG 1, the second for SDG 2, and so on.
                ```csv
                10
                5
                12.5
                ... (up to 17 lines)
                ```
            2.  **Indexed Format:** Each line contains `SDG_Index,Value` (e.g., `1,10` or `17,5.5`). The SDG Index should be 1-17. Order doesn't matter, and not all SDGs need to be present.
                ```csv
                1,10
                5,16
                17,8.2
                ```
        *   In the "Upload Data (CSV)" section, click "Choose File" and select your CSV.
        *   The graph and controls will update with the loaded data. A status message will indicate success or any parsing issues.
4.  **View the Graph:** The circular graph on the right will update in real-time as you change values.
5.  **Download as SVG:**
    *   Click the "Download as SVG" button below the graph.
    *   An SVG file named `sdg_height_chart.svg` will be downloaded to your computer.

## File Structure

*   `index.html`: The main HTML file containing the structure, CSS styles, and JavaScript logic for the application.

## Technical Details

*   **Frontend:** HTML, CSS, JavaScript (Vanilla JS)
*   **Graphics Rendering:**
    *   **Canvas API:** Used for the interactive real-time display of the graph.
    *   **SVG (Scalable Vector Graphics):** Generated dynamically for the downloadable chart, ensuring high quality and scalability. Text on a path (`<textPath>`) is used for curved labels in the SVG.
*   **CSV Parsing:** Handled by client-side JavaScript using the `FileReader` API.

## Customization & Development

*   **SDG Colors and Names:** These are defined in the `SDGs` array in the JavaScript section. You can modify them if needed.
*   **Graph Aesthetics:** Constants like `baseRadius`, `maxExtension`, `TEXT_GUIDE_RADIUS`, and colors within the JavaScript can be adjusted to change the visual appearance.
*   **Further Features:** The code is well-commented and structured to allow for easier extension (e.g., adding tooltips with full SDG names on hover, different chart types, etc.).

## To Run Locally

1.  Clone this repository or download the `index.html` file.
2.  Open `index.html` in any modern web browser (Chrome, Firefox, Edge, Safari).

## Potential Future Enhancements

*   Tooltips on graph segments showing full SDG names and values.
*   Option to customize SDG colors directly in the UI.
*   Saving/loading chart configurations (e.g., to local storage).
*   More advanced CSV parsing options or error handling.
*   Different chart styles or representations.

## License

This project is open source. Feel free to use, modify, and distribute.
