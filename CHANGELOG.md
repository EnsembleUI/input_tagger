3.0.1

Improved overlay positioning with center alignment
Added horizontal centering for overlay with fixed width
Added overlayWidth property to control the width of the suggestion overlay
Fixed overlay positioning with proper screen-center alignment

## 3.0.0

* Migrated package to EnsembleUI organization
* Fixed tag deletion behavior when cursor is positioned within tag boundaries
* Fixed edge case where deleting text near adjacent tags could cause errors
* Enhanced overlay behavior to hide properly when cursor interacts with tags

## 2.1.0

* Added `isInitialTag` property to controller for better control over initial tag state
* Enhanced search prevention logic to check both cursor position and initial tag state
* Fixed tag deletion behavior by removing unnecessary defer calls
* Improved trie data structure management after tag removal
* Enhanced overlay hiding logic with additional initial tag state checks
* Prevented search activation when controller indicates initial tag presence
* Fixed edge cases in tag manipulation when dealing with initial tags

## 2.0.1

* Added direct tag deletion when cursor is positioned within tag boundaries
* Fixed out-of-range errors when deleting text near adjacent tags
* Improved overlay behavior to automatically hide when cursor enters a tag
* Enhanced cursor position handling for better backspace behavior
* Fixed edge cases with tag boundary detection (added +2 offset for more accurate detection)
* Prevented search activation when cursor is inside existing tags
* Refined search regex pattern to exclude spaces for more precise matching
* Added print debugging for better tag parsing visibility (development feature)
* Improved overall stability when manipulating text around tag boundaries

## 2.0.0

* Improved tag formatting with better nested tag handling
* Added direct tag deletion when cursor is within a tag
* Enhanced default pattern handling with sensible defaults
* Optimized formatted text generation for better performance
* Fixed tag selection and cursor positioning issues
* Improved tag retrieval with optimized implementation

## 0.0.1

* Initial release of input_tagger
* Support for tags with spaces
* Multiple trigger characters (@, #, etc.)
* Customizable tag styles
* Dynamic overlay for tag suggestions
* Easy integration with existing text fields