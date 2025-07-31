+++
title = 'Wofi Hyprland Settings'
date = 2025-07-30T20:46:16-04:00
categories = ['Linux']
+++
## Wofi with UWSM in Hyprland

When using Hyprland with UWSM (Universal Wayland Session Manager), I found a setting to ensure that applications launched via wofi are properly managed by uwsm to integrate with systemd and ensure clean session management. This is also mentioned on Reddit.

Add the following keybind to your Hyprland configuration file (typically ~/.config/hypr/hyprland.conf):

bind = $mainMod, R, exec, uwsm app -- $(wofi --show drun --define=drun-print_desktop_file=true)

The wofi --show drun --define=drun-print_desktop_file=true command ensures that wofi outputs the selected application's desktop file path, which uwsm app -- can then use to launch the application as a systemd unit.
