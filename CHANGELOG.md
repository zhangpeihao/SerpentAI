## 0.1.12b1

* FIX - inceptionv3 context classifier is now using the newer normalize function instead of the old scale_range one
* REFACTOR / FIX - added a mechanism to handle scancodes for extended keys in NativeWin32 input controller. Fixes arrow keys on Windows :)
* FIX - added a dtype kwarg to FrameGrabber get_frames. necessary when using 'FLOAT' pipeline operator

## 0.1.11b1

* FEATURE - added 'FLOAT' operator in frame transformation pipelines (needed for DQN)
* FEATURE - added 'SSIM' mode to sprite identifier
* FIX - sprite identifier score thresholds now work consistently with all offered modes
* FIX - resolved an issue with sprite identifier constellation of pixels mode and sprites with alpha channel
* FIX - added macOS command key to KeyboardKey enum and added a mapping for PyAutoGUI input controller backend
* FIX - linux window controller will now only consider visible windows when attempting to find game windows
* FEATURE - better range normalization in serpent.cv: ability to pass in target domain

## 0.1.10b1

* FEATURE - added frame transformation pipelines
* FIX - DQN and DDQN fixes and Windows compatibility tweaks

## 0.1.9b1

* FIX - emptied out __init__.py for serpent.input_controllers (AKA win32api trying to import on Linux)

## 0.1.8b1

* MAJOR CHANGE - added a KeyboardKey enum containing all valid keys that can be pressed on a standard keyboard; all InputController methods that accept keys now require KeyboardKey items
* FEATURE - added a fully-compliant native Windows input controller that uses the SendInput DLL function
* FEATURE - added 'move', 'click_down' & 'click_up' to the InputController protocol; implemented them in PYAUTOGUI & NATIVE_WIN32
* FEATURE - context classifier validation during training can now be skipped
* FEATURE - context classifier model checkpoints can now be autosaved
* FEATURE - locate() from the SpriteLocator can now use screen regions
* FIX - prevented an empty list to get to a min() call in locate_string

## 0.1.7b1

* FIX - macOS frame reshape error should be resolved; Including the top bar as part of the capture until someone can a programmatic way to get the inner window size.
* FEATURE - added a Web Browser GameLauncher for people who want to tackle web games
* FIX - Added a default static seed to the the training of the context classifier dataset split operation

## 0.1.6b1

* REFACTOR - InputController now pivots on a backend to allow extension; PyAutoGUI extracted to a backend (default)
* FIX - no CUDA initialization unless it's actually needed
* FEATURE - new `serpent window_name` command to assist in finding the proper kwargs["window_name"] for Game plugins
* FIX - stopped initializing a VisualDebugger instance on every new GameFrameBuffer. Huge performance gain in frame consumption rate.

## 0.1.5b1

* FIX - DarwinWindowController is_window_focused should use process title and not name

## 0.1.4b1

* FIX - initial applescript to find focused windows was fine but macOS users need to use process name and not the window name

## 0.1.3b1

* FEATURE - added resize_window to all WindowController classes
* TWEAK - Base Game Agent GameFrameLimiter FPS to 30

## 0.1.2b1

* FEATURE - retina display detection and handling on macOS
* FIX - most mouse events were missing the window geometry offsets
* FIX - replaced the applescript used to determine the focused window so the visible title bar name can be used in all cases

## 0.1.1b1

* FIX - conda not found on Windows serpent setup
* FIX - version locked Cython to version 0.26.1 because Kivy doesn't build on 0.27

## 0.1.0b1

* Initial Beta Release