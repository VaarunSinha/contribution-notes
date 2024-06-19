# Ticket 35404

## Issues Left

 1. input type=text boxes on the right side grow in height if the label doesn't fit into 160px.
 2. checkboxes are not aligned with their labels

### Checkbox Issue 

![The issue](https://i.ibb.co/4R4ys2J/Screenshot-2024-06-19-at-10-06-49-AM.png)

This issue only exists on Desktop Screen Sizes, but not on Tablets or Mobiles:

![Screenshot-2024-06-19-at-10-33-22-AM](https://i.ibb.co/nr74cVr/Screenshot-2024-06-19-at-10-33-22-AM.png)

The cause of this issue:

![enter image description here](https://i.ibb.co/GdSQbJS/Screenshot-2024-06-19-at-10-08-15-AM.png)

Is padding in the bottom of the class known as : `.vCheckboxLabel`

```css
.aligned  .vCheckboxLabel {

float: none;

width: auto;

display: inline-block;

vertical-align: -3px;

padding: 0  0  5px  5px;

}
```
This bottom padding doesn't exist in mobile and tablet devices, so the checkbox and label are aligned

![enter image description here](https://i.ibb.co/Bf8jGmZ/Screenshot-2024-06-19-at-10-08-44-AM.png)

The solution is to remove the bottom padding:
```css
.aligned  .vCheckboxLabel {

float: none;

width: auto;

display: inline-block;

vertical-align: -3px;

padding: 1px  0  0 5px;

}
```

But as you might have noticed the only padding remaining is the left one so why the shorthand?

It's because if we do padding-left then the padding of top is set to something other than 1px therefore hampering the alignment.

This solution is already running in mobile and tablet screens, the same solution needs to be applied in Desktop. (Removal of bottom padding)

#### Difference and exact contribution

![alt text](https://i.ibb.co/Q67Mf6H/Screenshot-2024-06-19-at-10-37-30-AM.png)
