# ARB generator

Generates Flutter ARB files from `languagelist` and PO files.

## Installation

```
dart pub global activate --source path .
```

## Automatic generation

Run `/path/to/script/arbgen.sh <path/to/pofiles>` to recursively scan a
directory for PO files, and generate matching ARB files in the current working
directory.

## Manual generation

### Language files

Generate `foo_*.arb` from a [`languagelist`](https://git.launchpad.net/ubiquity/tree/d-i/source/localechooser/languagelist) file:

```bash
$ arbgen /path/to/languagelist --prefix foo --output /path/to/lib/l10n
```

### Translation files

Generate `app_*.arb` from a directory of [PO files](https://git.launchpad.net/ubiquity/tree/debian/real-po).

```bash
$ arbgen /path/to/po/directory --output /path/to/lib/l10n
```

**NOTES**:
- The command can be repeated for multiple input directories.
- The `l10n` output directory must contain `app_en.arb` for the generator to be able to match PO and ARB translation entries.
