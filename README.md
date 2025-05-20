# input_tagger

A Flutter widget that provides tagging capabilities with improved support for spaces in tags. This package makes it easy to implement mention systems, hashtags, and other tagging features in your Flutter applications.

## Features

* Support for tags with spaces (like "John Smith" or "New York")
* Multiple trigger characters (@, #, etc.) with customizable styling
* Intelligent tag handling that preserves formatting during text editing
* Smart cursor positioning that prevents accidental tag modifications
* Dynamic overlay for tag suggestions with customizable positioning
* Robust tag deletion and boundary detection
* Optimized tag formatting with nested tag support
* Easy integration with existing text fields

## Getting started

Add the package to your pubspec.yaml:

```yaml
dependencies:
  input_tagger: ^3.0.1
```

Run `flutter pub get` to install the package.

## Usage

```dart
import 'package:input_tagger/input_tagger.dart';

// Create a controller
final taggerController = InputTaggerController();

// Use the widget
InputTagger(
  controller: taggerController,
  overlay: YourCustomOverlayWidget(),
  onSearch: (query, triggerCharacter) {
    // Handle search for tags
    print('Searching for $query triggered by $triggerCharacter');
  },
  builder: (context, textFieldKey) {
    return TextField(
      key: textFieldKey,
      decoration: InputDecoration(
        hintText: 'Type @ to mention someone',
      ),
    );
  },
  triggerCharacterAndStyles: {
    '@': TextStyle(color: Colors.blue),
    '#': TextStyle(color: Colors.green),
  },
  tagTextFormatter: (id, tag, triggerCharacter) {
    return "$triggerCharacter$tag"; // Customize how tags appear in text
  },
)
```

## Advanced Usage

You can customize various aspects of the InputTagger:

```dart
InputTagger(
  controller: taggerController,
  overlay: YourCustomOverlayWidget(),
  onSearch: (query, triggerCharacter) {
    // Show suggestion overlay
  },
  builder: (context, textFieldKey) {
    return TextField(key: textFieldKey);
  },
  padding: EdgeInsets.all(8.0),
  overlayHeight: 300,
  overlayPosition: OverlayPosition.bottom,
  triggerStrategy: TriggerStrategy.eager,
  searchRegex: RegExp(r'^[a-zA-Z0-9\s]*$'), // Allow spaces in search
  triggerCharacterAndStyles: {
    '@': TextStyle(color: Colors.blue, fontWeight: FontWeight.bold),
    '#': TextStyle(color: Colors.green, fontStyle: FontStyle.italic),
  },
)
```

## Adding and Managing Tags Programmatically

```dart
// Add a tag
taggerController.addTag(id: 'user123', name: 'John Smith');

// Set initial tag state
taggerController.isInitialTag = true; // Prevents unwanted search activation

// Clear all tags
taggerController.clear();

// Get formatted text with tags
String text = taggerController.formattedText;

// Access all current tags
final tags = taggerController.tags;

// Dismiss the overlay
taggerController.dismissOverlay();
```

## Additional information

For issues, feature requests, or contributions, please visit the [GitHub repository](https://github.com/EnsembleUI/input_tagger).

This package is licensed under the MIT License - see the LICENSE file for details.
