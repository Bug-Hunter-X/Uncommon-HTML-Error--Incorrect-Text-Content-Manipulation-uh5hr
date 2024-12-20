# Uncommon HTML Error: Incorrect Text Content Manipulation

This repository demonstrates a subtle but important distinction in how to modify the content of HTML elements using JavaScript.  Incorrectly using `textContent` can lead to unexpected loss of HTML structure, while `innerHTML` offers flexibility but demands careful handling to prevent Cross-Site Scripting (XSS) vulnerabilities.

## Bug Description
The `bug.html` file shows an example where attempting to directly change the content using `textContent` removes existing HTML structure. The `bugSolution.html` shows the correct approach.  It's crucial to use `innerHTML` when changing content that includes HTML tags, and to sanitize user inputs when dealing with dynamically generated content.

## How to reproduce the bug:
1. Open the `bug.html` file in a browser.
2. Observe that after the script runs, the text content is correctly changed but the original element is replaced rather than simply changed, in some browsers and cases.

## Bug Solution
The `bugSolution.html` file illustrates the correct approach. We leverage `innerHTML` to properly modify the HTML content. Remember that using `innerHTML` with unsanitized user input can introduce XSS vulnerabilities, which need to be addressed appropriately.