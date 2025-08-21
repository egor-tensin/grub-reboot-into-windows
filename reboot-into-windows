#!/usr/bin/env bash

set -o errexit -o nounset -o pipefail
shopt -s inherit_errexit lastpipe

readonly cfg_path=/boot/grub/grub.cfg

get_windows_menu_entry() {
     local windows_entries
     windows_entries="$( awk -F\' '/menuentry / {print $2}' "$cfg_path" | grep -Fi Windows )"

     local numof_entries
     numof_entries="$( echo "$windows_entries" | wc -l )"

     if [ "$numof_entries" -ne 1 ]; then
         echo "Don't know which one of the following entries to select:" >&2
         echo "$windows_entries" >&2
         return 1
     fi

     echo "$windows_entries"
}

main() {
    local entry
    entry="$( get_windows_menu_entry )"

    # grub-reboot returns 0 even if something like a permission error happens.
    # It does print something in that case though, and nothing after a
    # successful termination.
    local output
    output="$( grub-reboot "$entry" )"

    if [ -n "$output" ]; then
        echo "grub-reboot probably exited with an error:" >&2
        echo "$output" >&2
        return 1
    fi

    reboot
}

main
