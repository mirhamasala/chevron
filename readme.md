# The Chevron

## Instructions from Lars

I made this a few days ago, when you click the chevron `>` the block beneath it becomes visible and when you click it again it toggles back to hidden.

It’s pure CSS, no JavaScript at all. Can you tell me how I did it? Or make one yourself.

The simplest form is between 10 and 20 lines of CSS. If it gets much more than that ask me and explain your process.

![chevron](chevron.png)

## Round 1

1. The `<input type="checkbox">` is the right way to go. When a checkbox input is ‘checked’ it triggers a pseudo selector called `:checked` You can listen to `:checked` in order to hide or show elements.

2. Then there’s another thing, a label is connected by `id` to an input. That means that if you click the label, the input toggles.

In this case you can hide the actual input, because you don’t need it for this. In the label text you can put the *chevron* `> see more`.

3. Finally, the order of elements matters because in CSS there are sibling selectors, `+` selects the next sibling, `~` selects all following siblings. But you can’t select a previous sibling or a parent. So the label, input and the element that you want to hide/show need to be adjacent siblings, in a certain order.

## Final Comments
*Q: For the owners boxes (the ones with the names), you're not using `display: flex`, right? Considering the `display: none`?*

A: For the gray boxes with the owners I use `display: grid;`, in a separate nested div

```html
<div class="unit-new-form">
    <div class="toggle-more">
        <input type="checkbox" name="view-more-ownership" id="view-more-ownership" class="view-more">
        <label for="view-more-ownership">...</label>
        <div class="additional-fields">
            <div class="owner-container">...</div>
        </div>
    </div>
</div>
```

```css
er {
    max-width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-auto-rows: 100px;
    grid-gap: 10px;
}
```

*Q: In your real project, did you draw the chevron using CSS?*

A: In my real project I used a Font Awesome chevron <https://fontawesome.com/icons/chevron-right?style=solid>
I normally wouldn’t draw a lot with CSS, I’d use an SVG in that case (you can also manipulate those with CSS/JavaScript) if you do want to draw with CSS then you can find a few basic shapes here, but they’re always a bit hacky <https://css-tricks.com/the-shapes-of-css/>

Q: Any details that caught your attention while looking at my code? Naming? Use of selectors?

A:Your code is fine, it’s quite an improvement in terms of structure in comparison to what you showed me earlier. I don’t really have any remarks in this, the only thing I noticed is that you used `-webkit-transform: rotate(90deg);` instead of just `transform: rotate(90deg);`

## Resources
[Can I have an onclick effect in CSS?](https://stackoverflow.com/questions/13630229/can-i-have-an-onclick-effect-in-css)

[Child and Sibling Selectors](https://css-tricks.com/child-and-sibling-selectors/)

[How do you order your CSS properties](https://css-tricks.com/poll-results-how-do-you-order-your-css-properties/)
