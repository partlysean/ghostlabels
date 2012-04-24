# Ghost Labels

A small bit of Javascript (powered by jQuery) for creating cool inline form field labels.

I built this because all the other inline label plugins I've tried are quirky and buggy and didn't provide a really great experience.
Ghost Labels is better. That said, if you see some improvements that can be made to the Javascript, by all means fork this project. 

Also, I considered turning this into a jQuery plugin, but setup is just as straightforward and I don't have to re-write anything.

## The HTML (Piece 1/3)

Write your HTML as you normally would when using `<label>` and `<input>`. To achieve the inline effect, the label needs to be absolutely
positioned over its associated input, so wrapping both the label and input in something set to `position: relative;` is necessary.
The CSS we write will achieve the positioning for us, but your markup for a label/input group should look something like this:

    <div class="ghost-label">
        <label for="first-name">First Name</label>
        <input type="text" id="first-name" />
    </div>

## The CSS (Piece 2/3)

CSS is used for positioning and aligning the label over the field. I have the `top` and `left` properties set to `0` for now, but you'll
want to tweak those values depending on how your inputs are styled for your website. The best way to sell this effect is to have the
font family, weight, size, etc. for both the label and the input exactly the same - that way nothing shifts when text is entered into the field.

    .ghost-label {
        position: relative;
    }

    .ghost-label label {
        position: absolute;
        top: 0;
        left: 0;
        cursor: text;
    }

## The Javascript (Piece 3/3)

Of course, the Javascript is what makes all this work. There's no need to go in-depth on how the Javascript works, so you can look at
the source file if you're curious. I'll admit the Javascript could be a bit more concise and efficient, but it's in good working order.

To implement, simply link to jQuery and the `ghostlabels.js` script at the bottom of your HTML document before the closing body tag (`</body>`).

    <!-- JQUERY -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
    
    <!-- GHOST LABELS -->
    <script src="ghostlabels.js"></script>