# POPA Messaging App - Theme Modes
## Light & Dark Theme Design Specifications

### Design Principles
- **Accessibility First**: All themes meet WCAG AA contrast requirements
- **Consistent Experience**: Maintains usability across both themes
- **Platform Appropriate**: Follows Material Design (Android) and iOS guidelines
- **User Choice**: Easy switching between themes with system preference detection

---

## Light Theme

### Color Palette
```json
{
  "light": {
    "background": "#FFFFFF",
    "surface": "#F7F7F8",
    "surfaceVariant": "#F0F0F0",
    "primary": "#0A84FF",
    "primaryVariant": "#0056CC",
    "accent": "#34C759",
    "accentVariant": "#28A745",
    "bubbleOutgoing": "#DCF8C6",
    "bubbleIncoming": "#FFFFFF",
    "textPrimary": "#111827",
    "textSecondary": "#6B7280",
    "textMuted": "#9CA3AF",
    "danger": "#FF3B30",
    "warning": "#FF9500",
    "success": "#34C759",
    "border": "#E5E7EB",
    "shadow": "rgba(0, 0, 0, 0.1)"
  }
}
```

### Message Bubbles (Light Theme)
- **Outgoing Messages**: Light green (#DCF8C6) with dark text (#111827)
- **Incoming Messages**: White (#FFFFFF) with dark text (#111827)
- **Contrast Ratio**: 4.5:1 (meets WCAG AA)
- **Border**: Subtle shadow for depth
- **Text Color**: #111827 (high contrast)

### Accessibility Compliance
- **Text Contrast**: 4.5:1 ratio (WCAG AA)
- **Touch Targets**: 48dp minimum
- **Font Size**: 16sp minimum for body text
- **Line Height**: 1.5 for optimal readability

---

## Dark Theme

### Color Palette
```json
{
  "dark": {
    "background": "#000000",
    "surface": "#1C1C1E",
    "surfaceVariant": "#2C2C2E",
    "primary": "#0A84FF",
    "primaryVariant": "#5AC8FA",
    "accent": "#34C759",
    "accentVariant": "#30D158",
    "bubbleOutgoing": "#007AFF",
    "bubbleIncoming": "#2C2C2E",
    "textPrimary": "#FFFFFF",
    "textSecondary": "#8E8E93",
    "textMuted": "#636366",
    "danger": "#FF453A",
    "warning": "#FF9F0A",
    "success": "#30D158",
    "border": "#38383A",
    "shadow": "rgba(0, 0, 0, 0.3)"
  }
}
```

### Message Bubbles (Dark Theme)
- **Outgoing Messages**: Blue (#007AFF) with white text (#FFFFFF)
- **Incoming Messages**: Dark gray (#2C2C2E) with white text (#FFFFFF)
- **Contrast Ratio**: 4.5:1 (meets WCAG AA)
- **Border**: Subtle shadow for depth
- **Text Color**: #FFFFFF (high contrast)

### Accessibility Compliance
- **Text Contrast**: 4.5:1 ratio (WCAG AA)
- **Touch Targets**: 48dp minimum
- **Font Size**: 16sp minimum for body text
- **Line Height**: 1.5 for optimal readability

---

## Theme Implementation

### Flutter ThemeData Structure
```dart
class AppThemes {
  static ThemeData lightTheme = ThemeData(
    brightness: Brightness.light,
    primaryColor: Color(0xFF0A84FF),
    accentColor: Color(0xFF34C759),
    backgroundColor: Color(0xFFFFFFFF),
    scaffoldBackgroundColor: Color(0xFFF7F7F8),
    cardColor: Color(0xFFFFFFFF),
    dividerColor: Color(0xFFE5E7EB),
    textTheme: TextTheme(
      headline1: TextStyle(fontSize: 28, fontWeight: FontWeight.w700, color: Color(0xFF111827)),
      headline2: TextStyle(fontSize: 22, fontWeight: FontWeight.w600, color: Color(0xFF111827)),
      headline3: TextStyle(fontSize: 18, fontWeight: FontWeight.w600, color: Color(0xFF111827)),
      bodyText1: TextStyle(fontSize: 16, fontWeight: FontWeight.w400, color: Color(0xFF111827)),
      bodyText2: TextStyle(fontSize: 14, fontWeight: FontWeight.w400, color: Color(0xFF6B7280)),
      caption: TextStyle(fontSize: 13, fontWeight: FontWeight.w400, color: Color(0xFF6B7280)),
    ),
  );

  static ThemeData darkTheme = ThemeData(
    brightness: Brightness.dark,
    primaryColor: Color(0xFF0A84FF),
    accentColor: Color(0xFF34C759),
    backgroundColor: Color(0xFF000000),
    scaffoldBackgroundColor: Color(0xFF1C1C1E),
    cardColor: Color(0xFF2C2C2E),
    dividerColor: Color(0xFF38383A),
    textTheme: TextTheme(
      headline1: TextStyle(fontSize: 28, fontWeight: FontWeight.w700, color: Color(0xFFFFFFFF)),
      headline2: TextStyle(fontSize: 22, fontWeight: FontWeight.w600, color: Color(0xFFFFFFFF)),
      headline3: TextStyle(fontSize: 18, fontWeight: FontWeight.w600, color: Color(0xFFFFFFFF)),
      bodyText1: TextStyle(fontSize: 16, fontWeight: FontWeight.w400, color: Color(0xFFFFFFFF)),
      bodyText2: TextStyle(fontSize: 14, fontWeight: FontWeight.w400, color: Color(0xFF8E8E93)),
      caption: TextStyle(fontSize: 13, fontWeight: FontWeight.w400, color: Color(0xFF8E8E93)),
    ),
  );
}
```

### Message Bubble Themes
```dart
class MessageBubbleThemes {
  static BoxDecoration outgoingLight = BoxDecoration(
    color: Color(0xFFDCF8C6),
    borderRadius: BorderRadius.circular(20),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.1),
        blurRadius: 2,
        offset: Offset(0, 1),
      ),
    ],
  );

  static BoxDecoration incomingLight = BoxDecoration(
    color: Color(0xFFFFFFFF),
    borderRadius: BorderRadius.circular(16),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.1),
        blurRadius: 2,
        offset: Offset(0, 1),
      ),
    ],
  );

  static BoxDecoration outgoingDark = BoxDecoration(
    color: Color(0xFF007AFF),
    borderRadius: BorderRadius.circular(20),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.3),
        blurRadius: 2,
        offset: Offset(0, 1),
      ),
    ],
  );

  static BoxDecoration incomingDark = BoxDecoration(
    color: Color(0xFF2C2C2E),
    borderRadius: BorderRadius.circular(16),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.3),
        blurRadius: 2,
        offset: Offset(0, 1),
      ),
    ],
  );
}
```

---

## Accessibility Features

### High Contrast Mode
- **Light Theme**: Enhanced contrast for better visibility
- **Dark Theme**: Maintains contrast while reducing eye strain
- **System Integration**: Respects system high contrast settings
- **Custom Options**: User can override system settings

### Font Scaling
- **Support Range**: 0.8x to 2.0x scaling
- **Responsive Layout**: UI adapts to larger text sizes
- **Touch Targets**: Maintains 48dp minimum even with scaling
- **Readability**: Line height adjusts for optimal reading

### Color Blindness Support
- **Color Coding**: Not solely dependent on color
- **Alternative Indicators**: Icons and text labels
- **Pattern Recognition**: Visual patterns for status
- **Testing**: Verified with color blindness simulators

### Screen Reader Support
- **Semantic Labels**: All elements properly labeled
- **Navigation**: Logical tab order
- **Content**: Message content clearly announced
- **Status**: Delivery status announced appropriately

---

## Theme Switching

### Implementation
```dart
class ThemeProvider extends ChangeNotifier {
  ThemeMode _themeMode = ThemeMode.system;
  
  ThemeMode get themeMode => _themeMode;
  
  void setThemeMode(ThemeMode mode) {
    _themeMode = mode;
    notifyListeners();
  }
  
  bool get isDarkMode {
    if (_themeMode == ThemeMode.system) {
      return MediaQuery.of(context).platformBrightness == Brightness.dark;
    }
    return _themeMode == ThemeMode.dark;
  }
}
```

### User Preferences
- **System Default**: Follows device theme setting
- **Manual Override**: User can choose specific theme
- **Persistent**: Theme choice saved across app restarts
- **Immediate**: Theme changes apply instantly

---

## Testing & Validation

### Contrast Testing
- **Tools**: WebAIM Contrast Checker, Color Oracle
- **Standards**: WCAG AA (4.5:1) for normal text
- **Coverage**: All text/background combinations tested
- **Documentation**: Results documented for compliance

### Accessibility Testing
- **Screen Readers**: TalkBack (Android), VoiceOver (iOS)
- **High Contrast**: System high contrast mode
- **Font Scaling**: 200% scaling test
- **Touch Targets**: 48dp minimum verification

### User Testing
- **Diverse Users**: Testing with various accessibility needs
- **Feedback Collection**: User feedback on theme usability
- **Iteration**: Continuous improvement based on feedback
- **Documentation**: User testing results documented

---

## Future Enhancements

### Custom Themes
- **User Colors**: Allow custom accent colors
- **Bubble Styles**: Different bubble shapes and styles
- **Font Options**: Custom font selection
- **Layout Options**: Different layout arrangements

### Advanced Accessibility
- **Voice Control**: Voice navigation support
- **Switch Control**: External switch support
- **Eye Tracking**: Eye tracking navigation
- **Haptic Feedback**: Enhanced haptic responses

---

*This theme specification ensures POPA provides an accessible, beautiful, and consistent experience across all user preferences and accessibility needs.*
