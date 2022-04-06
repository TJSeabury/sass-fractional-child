# sass-middle-child
A useful mixin.


I've encountered the need to target the middle child on several occasions, and I've taken to using this sass mixin I wrote after referencing many stackoverflow questions, and their respective answers.

```sass
// Generate a reasonable number rules limited by $n.
@mixin middle-child($n) {
  // There is no middle for nChildren less than 3,
  // so lets just start at 3.
  @for $i from 3 to $n {
    // Find the middle, bias right for odd numbers.
    $mid: math.ceil(math.div($i, 2));
    // Select only those sets of children that number $i.
    &:first-child:nth-last-child(#{$i}) {
      // Select the middle child of that set.
      ~ :nth-child(#{$mid}) {
        @content; // Apply your styles.
      }
    }
  }
}
```
Usage:
```sass
.navigation {
  background-color: #ba0020;

  .nav-item {
    color: white;
    
    @include middle-child( 8 ) {
      font-weight: 900;
    }
  }
}
```
