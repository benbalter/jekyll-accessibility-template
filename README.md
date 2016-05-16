# Jekyll Voluntary Product Accessibility Template (VPAT) and §508 accessibility information template

## Usage

### Installation

#### If you have an existing Jekyll site

1. Copy `_data/accessibility.yml` to your site's `_data` folder
2. Copy `accessibility.md` to your site's source folder
3. Add the contents of `assets/style.css` to your site's CSS file

#### If you are creating a new Jekyll site

1. Fork this repository

### Customizing

You'll want to fill out the accessibility information in `_data/accessibility.yml`:

* You only need to fill out the `supports` and `comments` fields for each criterion
* `supports` must be one of:
  * "Supports"
  * "Supports with exceptions"
  * "Not applicable"
  * "Does not support"
* The comments section is optional, and is best used to describe how your product supports or doesn't support the crition
