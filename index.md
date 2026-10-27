The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Box Model Inspection</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <h1>CSS Box Model Showcase</h1>

    <div class="container">
        <!-- Box 1: Content-Box -->
        <div class="box box-one">
            <h2>Box One</h2>
            <p>This box uses standard content-box sizing with moderate padding and a solid border.</p>
        </div>

        <!-- Box 2: Border-Box -->
        <div class="box box-two">
            <h2>Box Two</h2>
            <p>This box uses border-box sizing with heavy padding and a dashed border.</p>
        </div>

        <!-- Box 3: Custom Spacing -->
        <div class="box box-three">
            <h2>Box Three</h2>
            <p>This box features a custom width, prominent border, and large outer margins.</p>
        </div>
    </div>

</body>
</html>
2. The CSS File (style.css)
CSS
body {
    font-family: Arial, sans-serif;
    background-color: #f4f6f9;
    color: #333333;
    padding: 20px;
    margin: 0;
}

h1 {
    text-align: center;
    color: #2c3e50;
    margin-bottom: 30px;
}

.container {
    max-width: 600px;
    margin: 0 auto;
}

/* Base box styles */
.box {
    background-color: #ffffff;
    border-radius: 6px;
}

/* Box 1: Content-Box (Default behavior) */
.box-one {
    box-sizing: content-box; /* Width applies only to content; padding and borders add to total size */
    width: 100%;
    padding: 15px;
    border: 3px solid #3498db;
    margin-bottom: 20px;
}

/* Box 2: Border-Box (Includes padding and border in element's total width/height) */
.box-two {
    box-sizing: border-box; 
    width: 100%;
    padding: 30px;
    border: 6px dashed #e74c3c;
    margin-bottom: 20px;
}

/* Box 3: Custom Width and Large Margins */
.box-three {
    box-sizing: border-box;
    width: 85%;
    padding: 20px;
    border: 4px solid #2ecc71;
    margin: 40px auto; /* Large top/bottom margin, auto centers horizontally */
}
3. Understanding content-box vs. border-box (Step 4)
box-sizing: content-box (Default): When you set a width or height, it applies only to the content area. Any padding or borders you add are added on top of that width, making the element physically larger than specified.

box-sizing: border-box: The specified width and height include the content, padding, and border. This makes layout math much easier because adding padding won't unexpectedly stretch your boxes past their containers.

4. Annotated Box Model Explanation (For Submission)
When you take your screenshot in Chrome DevTools (under the Elements > Computed tab), you can annotate the four layers from inside out:

Content (Innermost Layer):

What it is: The actual text or elements inside your HTML tags (e.g., your headings and paragraphs).

Padding:

What it is: The clear space surrounding the content, pushing the border outward. Box One has 15px of padding, while Box Two has 30px.

Border:

What it is: The line wrapped around the padding. Box One uses a 3px solid #3498db border, and Box Two uses a 6px dashed #e74c3c border.

Margin (Outermost Layer):

What it is: The empty space outside the border that pushes neighboring elements away. Box Three has a large 40px top and bottom margin (margin: 40px auto).