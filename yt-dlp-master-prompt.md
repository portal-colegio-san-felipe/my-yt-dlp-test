# PROJECT: My Personal yt-dlp Downloader & Visual Command Builder

Build a private, browser-based application using the official yt-dlp
software.

The application must function as a graphical interface and visual
command generator for yt-dlp. I want to control yt-dlp through buttons,
dropdowns, checkboxes and other interface elements rather than writing
commands manually.

I am not a programmer. You are responsible for the implementation,
technical decisions, testing and deployment using the capabilities
available in this environment.

## 1. Core requirements

The application must:

-   Run in a web browser.
-   Be hosted using the available free hosting capabilities.
-   Require no software installation on my personal Windows computer.
-   Require no local server, background helper, browser extension or
    native executable on my computer.
-   Use the official yt-dlp software to perform downloads.
-   Use FFmpeg for merging and audio conversion.
-   Have its own graphical interface.
-   Allow me to construct yt-dlp commands visually.
-   Support one active download at a time initially.

Do not enable paid services, subscriptions or billing without my
explicit permission.

Do not substitute third-party downloader services or unofficial yt-dlp
implementations.

## 2. Most important feature: Visual command builder

The central purpose of this application is to turn the official yt-dlp
documentation into an accessible graphical command builder.

Study the official documentation:

-   https://github.com/yt-dlp/yt-dlp
-   https://github.com/yt-dlp/yt-dlp#usage-and-options
-   https://github.com/yt-dlp/yt-dlp/wiki/FAQ
-   https://github.com/yt-dlp/yt-dlp/releases

Every implemented option must correspond to a real documented yt-dlp
feature or a properly implemented application-side feature.

Examples include:

  Feature              yt-dlp option
  -------------------- ---------------------
  Format selection     `-f`
  Extract audio        `-x`
  Audio conversion     `--audio-format`
  Audio quality        `--audio-quality`
  Embed subtitles      `--embed-subs`
  Download subtitles   `--write-subs`
  Download thumbnail   `--write-thumbnail`
  Embed metadata       `--embed-metadata`
  Output filename      `-o`
  Playlist download    `--yes-playlist`
  Single video         `--no-playlist`

These are examples, not the complete feature list.

### Command generation

The application must dynamically generate yt-dlp arguments based on my
selected settings.

For example:

-   Choosing MP3 should add the appropriate audio conversion arguments.
-   Choosing a maximum resolution should generate the appropriate
    format-selection expression.
-   Enabling metadata should add the appropriate metadata option.
-   Enabling subtitles should add the relevant subtitle options.

Include a live command preview that updates whenever I change a setting.

Include a button to copy the generated command.

Most importantly, the command preview and the actual backend execution
must use exactly the same generated argument configuration.

Never create controls that only change the appearance of the interface
without changing the actual download configuration.

Provide explanations of what each option does.

## 3. Development must happen in milestones

THIS IS A STRICT REQUIREMENT.

Do not attempt to build the entire application in one go.

Develop the application in the following six milestones.

Each milestone must be completed, tested and approved before starting
the next one.

Do not automatically advance to another milestone.

### MILESTONE 1 --- Technical feasibility and working download

This is the first and only milestone to implement initially.

Before building the complete application, verify that the actual hosting
environment can support the required functionality.

Tasks:

1.  Verify that the backend can download the official yt-dlp Linux
    executable.
2.  Verify that the executable can actually run in the hosting
    environment.
3.  Verify that FFmpeg can be installed and executed.
4.  Verify any additional JavaScript runtime requirements documented by
    yt-dlp.
5.  Implement a minimal browser interface with a URL field and download
    button.
6.  Execute an actual test download using yt-dlp.
7.  Make the resulting file downloadable through the browser.

Use a publicly accessible test video that we are authorized to download.

Acceptance criteria:

-   yt-dlp actually executes.
-   FFmpeg actually works.
-   An actual media file is downloaded.
-   The file is transferred successfully to the browser.
-   No fake download progress or simulated success.
-   No software installation is required on my personal computer.

If the hosting environment cannot execute external binaries, STOP.

Explain the specific limitation and do not proceed with a fake
implementation.

Once Milestone 1 works, report the results and wait for my approval.

### MILESTONE 2 --- Basic downloader interface

After approval, implement:

-   URL input.
-   Video download mode.
-   Audio download mode.
-   Basic quality selection.
-   Format selection.
-   Download button.
-   Real download progress.
-   Actual file delivery to the browser.

Acceptance criteria:

I must be able to download an actual video and an actual audio file
using the interface.

Wait for my approval before proceeding.

### MILESTONE 3 --- Visual command builder

Implement the main feature of this project.

Study the official yt-dlp documentation and progressively turn its
useful options into graphical controls.

Include:

-   Dynamic argument generation.
-   Live command preview.
-   Copy command functionality.
-   Explanations for options.
-   Organized settings categories.
-   Expandable advanced settings.

The command preview must accurately represent what the backend executes.

Wait for my approval before proceeding.

### MILESTONE 4 --- Advanced download functionality

Implement additional documented features, including:

**Video:** - Resolution filtering. - Format preferences. - Best
available quality. - Video/audio stream merging. - Subtitles. -
Thumbnail downloading. - Metadata embedding. - Custom filenames.

**Audio:** - MP3. - M4A. - WAV. - FLAC when supported. - Audio quality
selection. - Metadata embedding. - Thumbnail embedding when supported.

Only expose options that are actually implemented and supported.

Wait for my approval before proceeding.

### MILESTONE 5 --- Download management

Implement:

-   Download progress.
-   Download speed.
-   Estimated remaining time when available.
-   Cancellation.
-   Error reporting.
-   Download history.
-   Temporary file management.
-   Automatic cleanup.

Initially support one active download at a time.

Wait for my approval before proceeding.

### MILESTONE 6 --- Finalization and reliability

Implement:

-   Final interface improvements.
-   Authentication.
-   Secure backend execution.
-   Input validation.
-   Error recovery.
-   Automatic yt-dlp version checking and updating.
-   Testing across different supported video and audio formats.
-   Final deployment and reliability checks.

The final application must be usable as a daily personal downloader.

## 4. Technical architecture

Choose the architecture based on what the actual hosting environment
supports.

Preferred technologies:

-   React for the frontend.
-   Node.js for backend functionality.
-   Official yt-dlp standalone Linux binary.
-   FFmpeg.
-   Deno or another supported JavaScript runtime if required by current
    yt-dlp documentation.

Node.js can launch external programs using its built-in process
functionality.

Use safe process execution and pass arguments individually. Never
concatenate user input into shell commands.

The application must execute downloads remotely, not on my Windows
computer.

Do not require me to manually configure a VPS, install Docker, operate a
terminal or connect separate hosting services.

Use the integrated application building and deployment capabilities
available in this environment.

If the environment cannot satisfy these requirements within its free
hosting allowance, explain the problem rather than enabling paid
infrastructure.

## 5. Security and reliability

-   Only download yt-dlp from its official release source.
-   Verify downloaded executable integrity where possible.
-   Do not expose arbitrary command execution through the interface.
-   Validate URLs and settings.
-   Protect the application with appropriate authentication.
-   Do not request YouTube credentials or browser cookies by default.
-   Do not bypass DRM or access controls.
-   Clean up temporary files.
-   Report actual errors.
-   Never simulate successful downloads.
-   Never silently disable features that fail.

## 6. Rules for working with me

I am not a developer.

You must:

1.  Explain things in simple language.
2.  Make technical decisions yourself whenever possible.
3.  Avoid unnecessary technical questions.
4.  Never ask me to manually configure servers or execute complicated
    commands.
5.  Test your own work before presenting it.
6.  Clearly explain what I need to test.
7.  Wait for my feedback and approval before advancing milestones.

### CRITICAL: Preserve existing work

When moving between milestones:

-   Modify the existing project.
-   Preserve all previously working functionality.
-   Do not regenerate the application from scratch.
-   Do not replace working components unnecessarily.
-   Do not remove features without my permission.
-   Keep the project organized and maintainable.

If a new feature breaks an existing feature, fix the regression before
proceeding.

## 7. How to start

Begin with Milestone 1 ONLY.

Do not build the full interface yet.

First investigate the actual environment and determine whether the
official yt-dlp executable and FFmpeg can run successfully in the
deployed application.

Then build the smallest functional proof of concept and test an actual
download.

When finished, provide:

-   What you successfully implemented.
-   What you tested.
-   Whether the actual download worked.
-   Any limitations discovered.
-   What I need to test personally.

Then STOP and wait for my approval.

The goal is to build a reliable personal downloader progressively, not
to generate a large application that looks finished but does not work.
