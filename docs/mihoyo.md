# Mihoyo Games Startup cmdline parameters

Here're some cmdline parameters for Mihoyo games based on Unity engine.

## Genshin Impact

Unity 2017.4.30

### General args

1. `-adapter N` (Windows only)

    This allows the game to run full-screen on another display. The N maps to a Direct3D display adaptor. In most cases there is a one-to-one relationship between adapters and video cards. On cards that support multi-head (that is, they can drive multiple monitors from a single card) each “head” may be its own adapter.

    In higher version of Unity, `-monitor N` does what `-adapter N` can do. However, **`-monitor N` also has effect on Genshin Impact**.

2. `-screen-width N`

    Override the default screen width. This width value must be an integer from a **supported** resolution.

3. `-screen-height N`

    Override the default screen height. This must be an integer from a supported resolution.

4. `-screen-fullscreen N`

    Override the default full-screen state. `N` must be `0`(disable) or `1`(enable).

    When streaming with Sunshine, this arg should be `0`.

5. `-popupwindow`

    Create the window as a pop-up window, without a frame. This command isn’t supported on macOS.

    This parameter is useful, which solves the issue that the game window will minimize when loses focus.

For more args, see [Unity Manual](https://docs.unity3d.com/2017.4/Documentation/Manual/CommandLineArguments.html), though may not supported or have no effect.

### Unique args

1. `-is_cloud N`

    Enable(1) or disable(0, default) Cloud Genshin Impact support.

    [Snap.Hutao issue #1173](https://github.com/DGP-Studio/Snap.Hutao/issues/1173) said that this arg is **NOT** required for Cloud Genshin Impact.

2. `-platform_type PLATFORM_TYPE`

    If need Cloud Genshin Impact support, this arg is required.

    Known available `PLATFORM_TYPE`s:

    + `CLOUD_THIRD_PARTY_MOBILE` (will enable mobile UI on PC)
    + `CLOUD_THIRD_PARTY_PC`

3. `-use_mobile_platform`

    Use mobile UI.

Example for Cloud Genshin Impact(Mobile UI): `-is_cloud 1 -platform_type CLOUD_THIRD_PARTY_MOBILE -use_mobile_platform`

## Star Rail

Unity 2019.4.34

### General args

1. `-monitor N`

    Run Standalone Player on the specified monitor, indicated by a 1-based index number.

    How to get an exact `N`? From my investigation, it may be monitors index from left to right. **Need more investigation**.

2. `-screen-width N`

    Override the default screen width. This width value must be an integer from a **supported** resolution.

3. `-screen-height N`

    Override the default screen height. This must be an integer from a supported resolution.

4. `-screen-fullscreen N`

    Override the default full-screen state. `N` must be `0`(disable) or `1`(enable).

    When streaming with Sunshine, this arg should be `0`.

5. `-popupwindow`

    Create the window as a pop-up window, without a frame. This command isn’t supported on macOS.

    This parameter seems to have no effect on Star Rail, for Star Rail doesn't have the same issue I mentioned above.

For more args, see [Unity Manual](https://docs.unity3d.com/2019.4/Documentation/Manual/PlayerCommandLineArguments.html), though may not supported or have no effect.

**ATTENTION** The registry value `GraphicsSettings_PCResolution_h431323223` should be deleted in advance, otherwise specifying "-screen-fullscreen", "-screen-width" and "-screen-height" has no effect on Star Rail.

### Unique args

NOT FOUND YET
