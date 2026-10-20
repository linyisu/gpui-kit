# GPUI Windows platform patch

Source: crates.io `gpui-pre-windows` 0.3.9, upstream GPUI snapshot
`93d745668805029476e6d7fbb19652116fed51de`. Apache-2.0, license retained.
The published manifest is retained so consumers can patch this package without
copying it into their own source tree.

The DPI-change handler applies the outer rectangle supplied by Win32 and reads
the actual client size for rendering. It does not use the monitor work area as
an outer window rectangle. That would subtract invisible resize borders twice
and leave a desktop strip below maximized windows.

Consumers must point their root `[patch.crates-io].gpui-pre-windows` at this
repository commit. Cargo ignores dependency-local patches.
