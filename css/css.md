## What is "Float"?
Float is a CSS positioning property. To understand its purpose and origin, we can look to print design. In a print layout, images may be set into the page such that text wraps around them as needed. This is commonly and appropriately called "text wrap". Here is an example of that.

In web design, page elements with the CSS float property applied to them are just like the images in the print layout where the text flows around them. Floated elements remain a part of the flow of the web page.

Lets us position the an element to the left or the right of the parent element and removes itself from the normal document flow.

Initially designed to have text wrap around an image, but now it's used in many things like making text columns or grid gallerys.

```
image {
  float:left;
  margin: 10px
  }
```

When the height has been met, the element below resumes it's normal behavior.

left: The element must float on the left side of its containing block.

right: The element must float on the right side of its containing block.

none: The element must not float.

inline-start: The element must float on the start side of its containing block.


inline-end: The element must float on the end side of its containing block.

## Clearing Floats

In normal document flow, floats have no height. And therefore the parent div that encompasses all the divs within it will have no height, too.

We have to say to the normal document flow: hey there are floats above us and we want to clear them so we can restart stlying in the normal document flow after the floats.

so for the element that occurs after the floats we can addd:

```.content{
  clear: both;
  }
  ```

Usually we add an empty element below the floating element and add clear both to it.


OR

we can add within that div that contains floats a class 'after' which literally means after the div
```.services.after{
  content: "",
  display:block,
  clear: both
}
```

This way we've dynamically added something AFTER that clears all of the floated element.

## Absolute positioning

This is distinctly different than page elements that use absolute positioning. Absolutely positioned page elements are removed from the flow of the webpage, like when the text box in the print layout was told to ignore the page wrap. Absolutely positioned page elements will not affect the position of other elements and other elements will not affect them, whether they touch each other or not.

## The key technical differences between an abstract class and an interface are:

An Interface contains only the definition / signature of functionality, and if we have some common functionality as well as common signatures, then we need to use an abstract class. By using an abstract class, we can provide behavior as well as functionality both in the same time. Another developer inheriting abstract class can use this functionality easily, as they would only need to fill in the blanks.

Abstract classes can have constants, members, method stubs (methods without a body) and defined methods, whereas interfaces can only have constants and methods stubs.

Methods and members of an abstract class can be defined with any visibility, whereas all methods of an interface must be defined as public (they are defined public by default).

When inheriting an abstract class, a concrete child class must define the abstract methods, whereas an abstract class can extend another abstract class and abstract methods from the parent class don't have to be defined.

Similarly, an interface extending another interface is not responsible for implementing methods from the parent interface. This is because interfaces cannot define any implementation.

A child class can only extend a single class (abstract or concrete), whereas an interface can extend or a class can implement multiple other interfaces.

A child class can define abstract methods with the same or less restrictive visibility, whereas a class implementing an interface must define the methods with the exact same visibility (public).

## What are the differences between block, inline, and inline block display?

### Inline Elements

Inline elements don’t start on a new line, they appear on the same line as the content and tags beside them. Some examples of inline elements are ```<span> , <strong>, and <img> ``` tags.

When it comes to margins and padding, browsers treat inline elements differently. You can add space to the left and right on an inline element, but you cannot add height to the top or bottom padding or margin of an inline element.

### Inline-Block

Inline-block elements are similar to inline elements, except they can have padding and margins added on all four sides. You’ll have to declare display: inline-block in your CSS code.

### Block Element 

A block element always starts on a new line, and fills up the horizontal space left and right on the web page. You can add margins and padding on all four sides of any block element — top, right, left, and bottom.

## What is a pseudo-class?

A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s). For example, :hover can be used to change a button's color when the user hovers over it.

Pseudo-classes let you apply a style to an element not only in relation to the content of the document tree, but also in relation to external factors like the history of the navigator (:visited, for example), the status of its content (like :checked on certain form elements), or the position of the mouse (like :hover, which lets you know if the mouse is over an element or not).

```
selector:pseudo-class {
  property: value;
}
```

An element can match multiple pseudo-class selectors at the same exact time. That is the reason why the order of the pseudo-classes above is crucial.

We know that if two selectors are equal in specificity, by default, the selector farther down the stylesheet wins.

One situation where you can clearly see this issue is via a hyperlink element. Suppose that you hover your mouse pointer on the link, and then click on the link without moving your mouse afterwards. This situation means the link matches both :hover and :active selectors.

So if the :active style rule is above the :hover style rule — for instance — users will never get to see the :active style rule applied. This is because the :hover style rule will always overwrite it.

You can remember the ideal order by memorizing the acronym, LVHA. Link ? Visited ? Hover ? Active

## Difference between position absolute , static, relative and fixed .

Absolute — Positioning attributes values will be relative to the nearest parent element with relative (or absolute) positioning. If there is no such parent, it will default all the way back up to the <html> element itself.

Fixed — Fixed position element is positioned relative to the viewport. The viewport doesn’t change when the window is scrolled, so element will stay where it is when the page is scrolled.

Relative — Just setting position: relative will have no effect on it’s positioning , but if you do give it some other positioning attribute, say, top: 10px; it will shift it’s position 10 pixels down from where it would normally be.It limits the scope of absolutely positioned child elements.

Static — This is the default for every single page element.It just means that the element will flow into the page as it normally would.

## What is a Flexbox?

The Flexbox Layout officially called CSS Flexible Box Layout Module is new layout module in CSS3 made to improve the items align, directions and order in the container even when they are with dynamic or even unknown size. 

The prime characteristic of the flex container is the ability to modify the width or height of its children to fill the available space in the best possible way on different screen sizes.
