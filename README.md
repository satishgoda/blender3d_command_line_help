# Blender Command Line Help

> blender --help

    Blender 2.78 (sub 0)
    Usage: blender [args ...] [file] [args ...]

## Render Options:

> -b or --background

    Run in background (often used for UI-less rendering)

> -a or --render-anim

    Render frames from start to end (inclusive)

> -S or --scene <name>

    Set the active scene <name> for rendering

> -f or --render-frame <frame>

    Render frame <frame> and save it.
    
    * +<frame> start frame relative, -<frame> end frame relative.
    * A comma separated list of frames can also be used (no spaces).
    * A range of frames can be expressed using '..' seperator between the first and last frames (inclusive).


> -s or --frame-start <frame>

    Set start to frame <frame>, supports +/- for relative frames too.

> -e or --frame-end <frame>

    Set end to frame <frame>, supports +/- for relative frames too.

> -j or --frame-jump <frames>

    Set number of frames to step forward after each rendered frame

> -o or --render-output <path>

    Set the render path and file name.
    Use '//' at the start of the path to render relative to the blend-file.

    The '#' characters are replaced by the frame number, and used to define zero padding.

    * 'ani_##_test.png' becomes 'ani_01_test.png'
    * 'test-######.png' becomes 'test-000001.png'

    When the filename does not contain '#', The suffix '####' is added to the filename.

    The frame number will be added at the end of the filename, eg:
    # blender -b foobar.blend -o //render_ -F PNG -x 1 -a
    '//render_' becomes '//render_####', writing frames as '//render_0001.png'

> -E or --engine <engine>

    Specify the render engine
    use -E help to list available engines

> -t or --threads <threads>

    Use amount of <threads> for rendering and other operations
    [1-1024], 0 for systems processor count.


## Format Options:

> -F or --render-format <format>

    Set the render format, Valid options are...
            TGA RAWTGA JPEG IRIS IRIZ
            AVIRAW AVIJPEG PNG BMP
    (formats that can be compiled into blender, not available on all systems)
            HDR TIFF EXR MULTILAYER MPEG FRAMESERVER QUICKTIME CINEON DPX DDS JP2

> -x or --use-extension <bool>

    Set option to add the file extension to the end of the file


## Animation Playback Options:

> -a or --render-anim

    Render frames from start to end (inclusive)


## Window Options:

> -w or --window-border

    Force opening without borders

> -W or --window-borderless

    Force opening without borders

> -p or --window-geometry <sx> <sy> <w> <h>

    Open with lower left corner at <sx>, <sy> and width and height as <w>, <h>

> -con or --start-console

    Start with the console window open (ignored if -b is set), (Windows only)

> --no-native-pixels

    Do not use native pixel size, for high resolution displays (MacBook 'Retina')


## Game Engine Specific Options:

> -g Game Engine specific options

    -g fixedtime            Run on 50 hertz without dropping frames
    -g vertexarrays         Use Vertex Arrays for rendering (usually faster)
    -g nomipmap             No Texture Mipmapping
    -g linearmipmap         Linear Texture Mipmapping instead of Nearest (default)


## Python Options:

> -y or --enable-autoexec

        Enable automatic Python script execution

> -Y or --disable-autoexec

        Disable automatic Python script execution (pydrivers & startup scripts), (compiled as non-standard default)

> -P or --python <filename>

        Run the given Python script file

> --python-text <name>

        Run the given Python script text block

> --python-expr <expression>

        Run the given expression as a Python script

> --python-console

        Run blender with an interactive console

> --python-exit-code

        Set the exit-code in [0..255] to exit if a Python exception is raised
        (only for scripts executed from the command line), zero disables.

> --addons

        Comma separated list of add-ons (no spaces)


## Debug Options:

> -d or --debug

        Turn debugging on

        * Enables memory error detection
        * Disables mouse grab (to interact with a debugger in some cases)
        * Keeps Python's 'sys.stdin' rather than setting it to None

> --debug-value <value>

        Set debug value of <value> on startup

> --debug-events

        Enable debug messages for the event system

> --debug-ffmpeg

        Enable debug messages from FFmpeg library

> --debug-handlers

        Enable debug messages for event handling

> --debug-libmv

        Enable debug messages from libmv library

> --debug-cycles

        Enable debug messages from Cycles

> --debug-memory

        Enable fully guarded memory allocation and debugging

> --debug-jobs

        Enable time profiling for background jobs.

> --debug-python

        Enable debug messages for Python

> --debug-depsgraph

        Enable debug messages from dependency graph

> --debug-depsgraph-no-threads

        Switch dependency graph to a single threaded evaluation

> --debug-gpumem

        Enable GPU memory stats in status bar

> --debug-wm

        Enable debug messages for the window manager, also prints every operator call

> --debug-all
        
        Enable all debug messages


> --debug-fpe

        Enable floating point exceptions

> --disable-crash-handler

        Disable the crash handler


## Misc Options:

> --factory-startup

        Skip reading the BLENDER_STARTUP_FILE in the users home directory


> --env-system-datafiles

        Set the BLENDER_SYSTEM_DATAFILES environment variable

> --env-system-scripts
        
        Set the BLENDER_SYSTEM_SCRIPTS environment variable

> --env-system-python

        Set the BLENDER_SYSTEM_PYTHON environment variable

> -nojoystick

        Disable joystick support

> -noglsl

        Disable GLSL shading

> -noaudio

        Force sound system to None

> -setaudio

        Force sound system to a specific device
        NULL SDL OPENAL JACK

> -h or --help

        Print this help text and exit

> -R

        Register blend-file extension, then exit (Windows only)

> -r

        Silently register blend-file extension, then exit (Windows only)

> -v or --version

        Print Blender version and exit

> --

        Ends option processing, following arguments passed unchanged. Access via Python's 'sys.argv'


## Other Options:

> /?

        Print this help text and exit (windows only)

> --disable-abort-handler

        Disable the abort handler

> -a <options> <file(s)>

        Playback <file(s)>, only operates this way when not running in background.
                -p <sx> <sy>    Open with lower left corner at <sx>, <sy>
                -m              Read from disk (Do not buffer)
                -f <fps> <fps-base>             Specify FPS to start with
                -j <frame>      Set frame step to <frame>
                -s <frame>      Play from <frame>
                -e <frame>      Play until <frame>

> --debug-freestyle

        Enable debug messages for FreeStyle

> --debug-gpu

        Enable gpu debug context and information for OpenGL 4.3+.

> --enable-new-depsgraph

        Use new dependency graph

> --enable-new-basic-shader-glsl

        Use new GLSL basic shader

> --verbose <verbose>

        Set logging verbosity level.


## Experimental Features:

> --enable-new-depsgraph

        Use new dependency graph

> --enable-new-basic-shader-glsl

        Use new GLSL basic shader


## Argument Parsing:

        Arguments must be separated by white space, eg:
        
        # blender -ba test.blend
        ...will ignore the 'a'
        
        # blender -b test.blend -f8
        ...will ignore '8' because there is no space between the '-f' and the frame value

### Argument Order:

        Arguments are executed in the order they are given. eg:
        # blender --background test.blend --render-frame 1 --render-output '/tmp'
        ...will not render to '/tmp' because '--render-frame 1' renders before the output path is set
        # blender --background --render-output /tmp test.blend --render-frame 1
        ...will not render to '/tmp' because loading the blend-file overwrites the render output that was set
        # blender --background test.blend --render-output /tmp --render-frame 1
        ...works as expected.

## Environment Variables:

    $BLENDER_USER_CONFIG      Directory for user configuration files.
  
    $BLENDER_USER_SCRIPTS     Directory for user scripts.

    $BLENDER_SYSTEM_SCRIPTS   Directory for system wide scripts.

    $BLENDER_USER_DATAFILES   Directory for user data files (icons, translations, ..).
    
    $BLENDER_SYSTEM_DATAFILES Directory for system wide data files.
    
    $BLENDER_SYSTEM_PYTHON    Directory for system python libraries.
    
    $TEMP                     Store temporary files here.
    
    $SDL_AUDIODRIVER          LibSDL audio driver - alsa, esd, dma.
    
    $PYTHONHOME               Path to the python directory, eg. /usr/lib/python.


