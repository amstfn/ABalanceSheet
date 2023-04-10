**In this project I work on tables**

**here are few steps of building page:**
1-
Screen readers announce HTML elements based on the document flow. We will eventually want the balance sheet to have a heading of "Balance Sheet" and a subheading of "AcmeWidgetCorp". However, this order does not make sense if announced by a screen reader.
 
Give your existing span the class attribute set to flex, and add two span elements within it. Give the first the text AcmeWidgetCorp. Give the second the text Balance Sheet. You will use CSS to reverse the order of the text on the page, but the HTML order will make more sense for a screen reader.

2-
Below your h1 element, create a div element. Give it an id attribute set to years. You want this particular element to be hidden from screen readers, so give it the aria-hidden attribute set to true.

3-
Below your existing div element, add a new div element with a class set to table-wrap. This will be the container for your tables.

Within that, add three table elements. You will be using CSS to style these into a single table, but using separate tables will help screen readers understand the document flow.

4-
HTML tables use the caption element to describe what the table is about. The caption element should always be the first child of a table, but can be positioned with the caption-side CSS property.

Add a caption element to your first table, and give it the text Assets.

5-
The thead and tbody elements are used to indicate which portion of your table is the header, and which portion contains the primary data or content.

Add a thead and tbody to your first table, below the caption element.

6-
The tr element is used to indicate a table row. Add a tr element within your thead element. In your new tr element, add a td element, followed by three th elements.

The td element indicates a data cell, while the th element indicates a header cell.

7-
Within each of your new th elements, nest a span element with the class set to sr-only year. Give them the following text (in order): 2019, 2020, and 2021.

Give your third th element the class attribute set to current.

Leave the td element empty. This element exists only to ensure your table has a four-column layout and associate the headers with the correct columns.

8-
Before you get too far into your styling, you should make use of the sr-only class. You can use CSS to make elements with this class completely hidden from the visual page, but still be announced by screen readers.

The CSS you are about to write is a common set of properties used to ensure elements are completely hidden visually.

The span[class~="sr-only"] selector will select any span element whose class includes sr-only. Create that selector, and give it a border property set to 0.

9-
The CSS clip property is used to define the visible portions of an element. Set the span[class~="sr-only"] selector to have a clip property of rect(1px, 1px, 1px, 1px).

The clip-path property determines the shape the clip property should take. Set the clip-path property to the value of inset(50%), forming the clip-path into a rectangle within the element.

10-
To prevent the text content from overflowing, give your span[class~="sr-only"] selector an overflow property set to hidden and a white-space property set to nowrap.

11-
Finally, you need to take these hidden elements out of the document flow. Give the span[class~="sr-only"] selector a position property set to absolute, a padding property set to 0, and a margin property set to -1px. This will ensure that not only are they no longer visible, but they are not even within the page view.

12-
The :first-of-type pseudo-selector is used to target the first element that matches the selector. Create an h1 .flex span:first-of-type selector to target the first span element in your .flex container. Remember that your span elements are reversed, visually, so this will appear to be the second element on the page.

Give your new selector a font-size property of 0.7em to make it look like a sub-heading.

12-
The calc() function is a CSS function that allows you to calculate a value based on other values. For example, you can use it to calculate the width of the viewport minus the margin of an element:

.example {
  margin: 10px;
  width: calc(100% - 20px);
}
Give #years a margin of 0 -2px, and a padding set to 0.5rem calc(1.25rem + 2px) 0.5rem 0.

13-
Adding position sticky moved the element into its own stack. To ensure your #years element does not get hidden by different stacks, add a z-index property set to 999 in the #years rule.

14-
Style the text within your #years element by creating a #years span[class] selector. The span[class] syntax will target any span element that has a class attribute set, regardless of the attribute's value.

Give your new selector a bold font, a width of 4.5rem, and text aligned to the right.

15-
Before you start diving in to the table itself, your span elements are currently bolded. Create a span:not(.sr-only) selector and give it a font-weight property set to normal.

The :not() pseudo-selector is used to target all elements that do not match the selector - in this case, any of your span elements that do not have the sr-only class. This ensures that your earlier rules for the span[class~="sr-only"] selector are not overwritten.

16-
Rather than having to constantly double-check you are not overwriting your earlier properties, you can use the !important keyword to ensure these properties are always applied, regardless of order or specificity.

Give each property in your span[class~="sr-only"] selector an !important keyword. Do not change any of the values.
Now that you have added the !important keyword, you can remove the :not(.sr-only) from your span selector.

17-
Create a table selector to target your tables. Set the border-collapse property to collapse, which will allow cell borders to collapse into a single border, instead of a border around each cell. Also set the border property to 0 to hide the borders themselves.

18-
Create a selector to target your td elements within your table body. Give them a width to fill the viewport, with a minimum and maximum of 4rem. This approach ensures that the width is fixed, whereas setting width specifically would allow the elements to shrink to the container.

19-
The [attribute="value"] selector targets any element that has an attribute with a specific value. Create a tr[class="total"] selector to target specifically your tr elements with the total class. Give it a bottom border of 4px double #0a0a23 and make the font bold.

20-
The key difference between tr[class="total"] and tr.total is that the first will select tr elements where the only class is total. The second will select tr elements where the class includes total.

In your case, tr.total will work. You can use this selector to target all td elements within your .total rows. Align the text to the right, and give them a padding of 0 0.25rem.

21-
The :nth-of-type() pseudo-selector is used to target specific elements based on their order among siblings of the same type. Use this pseudo-selector to target the third td element within your total table rows. Give it a right padding of 0.5rem.

22-
Your span elements now all have more specific styling, which means you can remove your span rule.
