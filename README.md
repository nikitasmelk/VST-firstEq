# VMESTE Matcha EQ

A professional-grade 3-band parametric equalizer audio plugin built with the JUCE framework. This VST3/AU plugin provides precise frequency control with real-time visualization and an intuitive user interface designed with a natural earth-tone color palette.

<!-- ![Plugin Interface](screenshots/plugin-interface.png) -->
*Plugin interface screenshots will be added once the plugin is built and tested*

## Features

### Core Functionality
- **3-Band Parametric EQ**: Low-cut, peak/bell, and high-cut filters
- **Real-time Frequency Analyzer**: Visual feedback of your audio's frequency content
- **Professional Controls**: Precise parameter adjustment with smooth automation support
- **Bypass Options**: Individual bypass switches for each filter section
- **Modern UI**: Clean, professional interface with custom earth-tone color scheme

### Filter Specifications

#### Low-Cut Filter
- **Frequency Range**: 20 Hz - 20 kHz
- **Slope Options**: 12, 24, 36, or 48 dB/octave
- **Default**: 20 Hz, 12 dB/oct
- **Use Case**: Remove unwanted low-frequency content, rumble, and mud

#### Peak/Bell Filter
- **Frequency Range**: 20 Hz - 20 kHz
- **Gain Range**: ±24 dB
- **Q Range**: 0.1 - 10.0
- **Default**: 750 Hz, 0 dB gain, Q=1.0
- **Use Case**: Boost or cut specific frequency ranges, tone shaping

#### High-Cut Filter
- **Frequency Range**: 20 Hz - 20 kHz
- **Slope Options**: 12, 24, 36, or 48 dB/octave
- **Default**: 20 kHz, 12 dB/oct
- **Use Case**: Remove harsh highs, digital artifacts, or unwanted high-frequency content

### Real-Time Analyzer
- **FFT-based spectrum analysis** for both left and right channels
- **Toggle on/off** to save CPU when not needed
- **Visual feedback** to see the effect of your EQ adjustments
- **Dual-channel display** with different colors for left (green) and right (pale green) channels

## Screenshots

<!-- Screenshots will be added once the plugin is built and tested -->

**To be added:**
- Main plugin interface
- Detailed view of the control sections  
- Real-time frequency response visualization

*Build the plugin and load it in your DAW to see the actual interface with the custom earth-tone color palette and professional layout.*

<!-- 
![Main Interface](screenshots/plugin-interface.png)
*Main plugin interface*

![Controls Detail](screenshots/controls-detail.png)
*Detailed view of the control sections*

![Frequency Response](screenshots/frequency-response.png)
*Real-time frequency response visualization*
-->

## Installation

### System Requirements

#### macOS
- macOS 10.13 High Sierra or later
- Intel or Apple Silicon Mac
- DAW supporting VST3 or AU plugins

#### Windows
- Windows 10 or later (64-bit)
- DAW supporting VST3 plugins

### Pre-built Binaries

1. Download the latest release from the [Releases](https://github.com/nikitasmelk/VST-firstEq/releases) page
2. Extract the downloaded archive
3. Copy the plugin to your DAW's plugin directory:

#### macOS Installation Paths
```bash
# VST3
~/Library/Audio/Plug-Ins/VST3/VmesteBasedEQ.vst3

# Audio Unit
~/Library/Audio/Plug-Ins/Components/VmesteBasedEQ.component
```

#### Windows Installation Paths
```
# VST3 (64-bit)
C:\Program Files\Common Files\VST3\VmesteBasedEQ.vst3
```

### Building from Source

#### Prerequisites
- [JUCE Framework](https://juce.com/get-juce) (version 6.0 or later)
- Xcode (macOS) or Visual Studio 2019+ (Windows)
- CMake 3.15+ (optional, for CMake builds)

#### JUCE Modules Used
- `juce_audio_basics` - Basic audio functionality
- `juce_audio_devices` - Audio device handling
- `juce_audio_formats` - Audio file format support
- `juce_audio_plugin_client` - Plugin wrapper functionality
- `juce_audio_processors` - Audio processor base classes
- `juce_audio_utils` - Audio utility functions
- `juce_core` - Core JUCE functionality
- `juce_data_structures` - Data structure utilities
- `juce_dsp` - Digital signal processing modules
- `juce_events` - Event handling system
- `juce_graphics` - Graphics and drawing
- `juce_gui_basics` - Basic GUI components
- `juce_gui_extra` - Extended GUI components

#### Build Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/nikitasmelk/VST-firstEq.git
   cd VST-firstEq
   ```

2. **Open in Projucer (Recommended)**
   - Open `VmesteBasedEQ.jucer` in Projucer
   - Configure your target platform and IDE
   - Click "Save and Open in IDE"
   - Build the project in your IDE

3. **Alternative: Command Line Build**
   ```bash
   # macOS with Xcode
   xcodebuild -project Builds/MacOSX/VmesteBasedEQ.xcodeproj -configuration Release
   
   # Windows with Visual Studio
   msbuild Builds/VisualStudio2019/VmesteBasedEQ.sln /p:Configuration=Release
   ```

## Usage Guide

### Basic Operation

1. **Load the plugin** in your DAW on an audio track or bus
2. **Enable the analyzer** (button in top-right) to see your audio's frequency content
3. **Adjust the EQ bands** as needed:
   - Use the **Low-Cut** to remove unwanted low frequencies
   - Use the **Peak** band for tone shaping and problem frequency correction
   - Use the **High-Cut** to tame harsh highs or digital artifacts

### Parameter Controls

#### Rotary Knobs
- **Click and drag** vertically to adjust values
- **Double-click** to reset to default value
- **Shift+drag** for fine adjustment
- **Control/Cmd+click** for text entry

#### Bypass Buttons
- **Click** to toggle bypass for each filter section
- **Bypassed sections** are visually dimmed
- **Automation-friendly** for dynamic EQ effects

#### Analyzer Button
- **Toggle** the real-time frequency analyzer
- **Green waveform**: Left channel
- **Pale green waveform**: Right channel
- **Turn off** to save CPU when not needed

### Practical Applications

#### Mixing Applications
- **Kick Drum**: High-pass around 40-60 Hz, boost around 60-80 Hz for punch
- **Vocals**: High-pass around 80-100 Hz, presence boost around 2-5 kHz
- **Bass**: Low-pass around 100-150 Hz, definition boost around 1-2 kHz
- **Overhead/Cymbals**: High-pass around 300-500 Hz, air boost around 10-15 kHz

#### Mastering Applications
- **Gentle high-pass** around 20-30 Hz to clean up sub-bass
- **Subtle presence boost** around 2-4 kHz for clarity
- **Smooth high-frequency roll-off** to control harshness

#### Problem Solving
- **Muddy mix**: High-pass filters to remove unnecessary low end
- **Harsh vocals**: High-cut filter to smooth harsh frequencies
- **Thin instruments**: Peak boost in appropriate frequency range

## Technical Specifications

### Audio Processing
- **Sample Rate Support**: 44.1 kHz to 192 kHz
- **Bit Depth**: 32-bit floating point processing
- **Latency**: Zero latency (real-time processing)
- **CPU Usage**: Optimized for minimal CPU impact

### Plugin Formats
- **VST3**: Windows and macOS
- **Audio Unit (AU)**: macOS only
- **Standalone**: Not currently supported

### Parameters (Automation Support)
1. Low-Cut Frequency (20 Hz - 20 kHz)
2. Low-Cut Slope (12/24/36/48 dB/oct)
3. Low-Cut Bypass (On/Off)
4. Peak Frequency (20 Hz - 20 kHz)
5. Peak Gain (±24 dB)
6. Peak Quality/Q (0.1 - 10.0)
7. Peak Bypass (On/Off)
8. High-Cut Frequency (20 Hz - 20 kHz)
9. High-Cut Slope (12/24/36/48 dB/oct)
10. High-Cut Bypass (On/Off)
11. Analyzer Enable (On/Off)

## Development

### Project Structure
```
VST-firstEq/
├── Source/
│   ├── PluginProcessor.h      # Main audio processor
│   ├── PluginProcessor.cpp    # Audio processing implementation
│   ├── PluginEditor.h         # GUI components and layout
│   └── PluginEditor.cpp       # GUI implementation
├── VmesteBasedEQ.jucer        # JUCE project file
├── VmesteBasedEQ.filtergraph  # JUCE audio graph
├── screenshots/               # Plugin interface screenshots
├── LICENSE                    # MIT License
└── README.md                  # This file
```

### Code Architecture

#### Audio Processing (`PluginProcessor.cpp`)
- **Filter Chain**: Low-cut → Peak → High-cut processing chain using JUCE DSP modules
- **IIR Filters**: High-quality IIR (Infinite Impulse Response) filters for each band
- **Parameter Management**: JUCE AudioProcessorValueTreeState for automation and state management
- **Real-time Analysis**: FFT-based spectrum analysis using FIFO buffers for visualization
- **State Management**: Plugin state save/restore functionality with parameter versioning
- **Mono Chain Processing**: Separate processing chains for left and right channels

#### User Interface (`PluginEditor.cpp`)
- **Custom Look and Feel**: Earth-tone color palette (browns, greens, cream tones)
- **Rotary Sliders**: Custom `RotarySliderWithLabels` components with value display
- **Response Curve**: Real-time frequency response visualization with `ResponseCurveComponent`
- **Analyzer Display**: FFT spectrum display with dual-channel support using `PathProducer`
- **Color Scheme**: Professional design with colors like `darkBrown` (#605B56), `lightGreen` (#ACC18A), and `creamWhite` (#F2FBE0)
- **Bypass Buttons**: Custom `PowerButton` components for each filter section

### Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Credits

- **Developer**: nikitasmelkov
- **Framework**: [JUCE](https://juce.com/)
- **Company**: VMESTE (www.vmestetogether.com)

## Support

For support, feature requests, or bug reports, please open an issue on the [GitHub repository](https://github.com/nikitasmelk/VST-firstEq/issues).

---

**VMESTE Matcha EQ** - Professional audio processing made simple and beautiful.