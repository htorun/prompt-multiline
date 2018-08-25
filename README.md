# Prompt-Multiline

A bash script for a concise, multi-line color prompt inspired by [liquidprompt]
and based on information in [Bash Prompt HOWTO]

No | Color Scheme: Ubuntu Default | Color Scheme: Solarized Dark
-- | ---------------------------- | -----------------------
1  | ![prompt]                    | ![prompt solarized]
2  | ![prompt full]               | ![prompt full solarized]
3  | ![prompt root]               | ![prompt root solarized]

**1**: When in home directory, **2**: (Almost) full prompt, **3**: Superuser, **4**: User other than login user

**First prompt line**: `(chroot)user@machine:/working/dir`

**Second prompt line**: `[history-no](backgroun-jobs running/stopped)[git-info] [last retrun code]$ `

## Basic Usage

To test drive, clone the project:

```bash
git clone https://github.com/htorun/prompt-multiline.git
```

Source the bash script `prompt-multiline/prompt-multiline`:

```bash
source ./prompt-multiline/prompt-multiline
```

To return to the previous prompt enter `prompt_off`, and to turn the prompt-multiline
on again enter `prompt_on`.

To make it permanent, add the following lines to your `~/.bachrc` (replace `<install-path>`
with the path to `prompt-multiline` bash script

```bash
pm_path=<install-path>
if [ -f "$pm_path" ]; then
    # Only source multi-line prompt script when this is an interactive shell
    case "$-" in
        *i*)
            source "$pm_path"
            ;;
    esac
fi
unset pm_path
```

## License
Prompt-Multiline, Copyright 2018 Hami Torun <hamitorun@e-fabrika.net>

Licensed under the AGPL version 3

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

[prompt]: resources/prompt-multiline.png
[prompt solarized]: resources/prompt-multiline-solarized.png
[prompt full]: resources/prompt-multiline-full.png
[prompt full solarized]: resources/prompt-multiline-full-solarized.png
[prompt root]: resources/prompt-multiline-root.png
[prompt root solarized]: resources/prompt-multiline-root-solarized.png
[liquidprompt]: https://github.com/nojhan/liquidprompt.git
[Bash Prompt HOWTO]: https://www.tldp.org/HOWTO/Bash-Prompt-HOWTO/index.html

