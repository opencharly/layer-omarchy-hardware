# layer-omarchy-hardware

Omarchy hardware and laptop support as a charly layer — **dkms and vendor quirks**,
**machine-only, opt-in**, not yet populated.

## Status

This repo is a **scaffold**: it carries this `README.md` and the org-wide
`.github/workflows/tag-on-merge.yml` dispatcher, and **no `charly.yml` or candy yet**.
There is no `candy/omarchy-hardware/` to pin, and no image composes it. The scope
below is the intended role, recorded so the first candy lands against it.

## Intended scope

The machine-specific hardware enablement a laptop or desktop needs that the generic
Omarchy base deliberately omits: DKMS-managed out-of-tree kernel modules and
per-vendor quirk packages. It is machine-only and opt-in — a machine whose hardware
needs no quirk does not compose it, and no pod does.

## How it is meant to be consumed

Once populated, a machine image composes the candy by pinning its sub-path in the
nested `candy:` list:

```yaml
my-omarchy-machine:
  candy:
    base: omarchy
    candy:
      - '@github.com/opencharly/layer-omarchy-base/candy/omarchy-base:v2026.242.0701'
      - '@github.com/opencharly/layer-omarchy-hardware/candy/omarchy-hardware:<tag>'
```

## Layout

- `README.md` — this user overview.
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.

## Related

- Owning skill: none yet — `/charly-distros:omarchy-base` is the closest family
  owning procedure. The missing `skill:` entity is recorded against
  [opencharly/opencharly#291](https://github.com/opencharly/opencharly/issues/291).
- `/charly-distros:omarchy` — the Omarchy base image.
- `/charly-distros:omarchy-base` — the foundation layer.
- [`opencharly/opencharly`](https://github.com/opencharly/opencharly) — the umbrella.
