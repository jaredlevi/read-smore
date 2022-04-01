# Read-Smore

(cause read-more was already taken 😉)

A customizable, lightweight vanilla JS plugin for truncating content with a Read more / Read less move, whilst preserving the original markup. Able to truncate by max word or character count.


## Highlights:

- Super duper lightweight, no dependencies, vanilla js.
- Supports truncating content by max Word or Character count.
- Adds ellipse after truncated content.
- Preserves existing markup (nice).
- Read more / Read less text is customizable.
- Use data attributes to control max words/characters count.
- Block level class name is customizable.
- Read More text can be block level or inline viawwww provided css

[Docs / Demo](https://stephenscaff.github.io/read-smore)

## Install (via npm)

`npm i read-smore`

d
## Usage

#### Add to your project
```
import ReadSmore from 'read-smore'

const readMores = document.querySelectorAll('.js-read-smore')
ReadSmore(readMores).init()
```

#### Example markup - by max word count
```
<div 
  class="js-read-smore" 
  data-read-smore-words="70" 
>
  <p>Stuff and words and stuff and words.</p>
  <p>Words and stuff and words and stuff.</p>
  <!-- more HTML content -->
</div>
```

#### Example markup - by max character count
```
<div 
  class="js-read-smore" 
  data-read-smore-chars="150" 
>
  <p>Stuff and words and stuff and words.</p>
  <p>Words and stuff and words and stuff.</p>
  <!-- more HTML content -->
</div>
```

#### Provide Options
```
import ReadSmore from 'read-smore'

const readMores = document.querySelectorAll('.js-read-smore')

const options = {
  blockClassName: 'read-more',
  moreText: 'Custom more text',
  lessText: 'Custom less text'
}

ReadSmore(readMores, options).init()
```

### MarkUp
```
<article>
  <div class="read-more js-read-more" data-read-smore-count="60">
    <p><!-- some content call here --></p>
  </div>
</article>
```

## Caveats

Need to figure out how to handle ReadMore instances with ajaxed/Fetched in content, since the word count on existing instances will be already truncated.

Thinking the solution is to destroy and rebuild via a click event. Or, at least open all and rebuild on click.

## Todo
- Rename everything to 'ReadSmore'
- Provide callbacks on open/close
- Provide a destroy method
- Provide a solution for content injected after page load
- Add docs / demo pages via gh-pages
