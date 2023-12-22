# Scssとレスポンシブデザインの練習

## モバイルファーストの場合
_variables.scss内
```scss
$breakpoints: (
        "sm": "screen and (min-width: 400px)",
        "md": "screen and (min-width: 768px)",
        "lg": "screen and (min-width: 1000px)",
        "xl": "screen and (min-width: 1200px)",
) !default;
```
_functions.scss内
```scss
@mixin mq($breakpoint) {
  @media #{map-get($breakpoints, $breakpoint)} {
    @content;
  }
}
```

呼び出し
```scss
h3 {
    color: red;
    font-size: 1.4rem;
    
    @include mq(md) {
	color: blue;
	font-size: 1.6rem;
    }
}
```

## PCファーストの場合
_variable.scss内
```scss
$breakpoints: (
  "sm": "screen and (max-width: 399px)",
  "md": "screen and (min-width: 400px) and (max-width: 767px)",
  "lg": "screen and (min-width: 768px) and (max-width: 999px)",
  "xl": "screen and (min-width: 1000px)",
) !default;
```