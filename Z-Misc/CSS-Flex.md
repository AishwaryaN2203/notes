# CSS properties

## FLEX

### Flex Basics

> Flex has two direction - main axis and cross axis

Main axis is defined by

```
flex-direction
```

```
TO CHANGE DIRECTION
flex-direction :
 row row-reverse column column-reverse


flex-direction : columne-reverse

1 2 3

3
2
1

```

> An area of a document laid out using flexbox is called a flex container.
> To create a flex container, we set the value of the area's container's display property to flex or inline-flex.
> Direct children become the flex items

---

### Flex Multiline containers

> to wrap onto multiple lines

```
flex-wrap
```

values: wrap - nowrap(default)

### Flex Shorthand

```
flex-flow = flex-direction + flex-wrap
```

---

### Propertied applied to flex items

if we don't change the initial values then flexbox will put expty space after the last item

##### flex-basis

defines that sixe of that item in terms of the space it leaves as available space

##### flex-grow

set to positive integer - flex items can grow along the main axis

##### flex-shrink

set to positive integer - then items can become smaller than the flex-basis

---

### ALGIN - ITEMS

> will align the item on the cross axis

- align-item: default - stretch (full length of box)
- align-item: center
- align-item: flex-end (bottom left)
- align-item: flex - start( top left )

---

### justify-content

- justify-content : property is used to align items on the main axis
- justify-content: flex-start
- justify-content: flex-end
- justify-content: center
- justify-content: space-around - to cause an equal amount of sapce on right and left of each item
- justify-content: space-between - to take all the spare space after the items - pushes to the edges
- justify-content: space-evenly - to cause items to have equal space arounf them

---

#### Examples:

> TO PUT AN DIV ELEMENT TO THE CENTER OF PAGE
> display: flex;
> align-item: center;
> justify-content: center;
> top: 0px;
> bottom : 0px;
> right: 0px;
> left: 0px;
> position: absolute;
