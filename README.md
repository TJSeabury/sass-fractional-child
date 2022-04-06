# sass-middle-child
A useful mixin.


I've encountered the need to target the middle child on several occasions, and I've taken to using this sass mixin I wrote after referencing many stackoverflow questions, and their respective answers.

## Usage:
```scss
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
