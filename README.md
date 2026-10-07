# exav-samples

Sample files for [exav](https://github.com/sylvinus/exav)'s demos, kept out
of its repository so that its history stays small.

## Layout

- `viewer/`: the files the [@exav/viewer demo](https://exav.org/viewer/demo/)
  lists, and `viewer/samples.json`, which describes each one. The demo's
  sidebar is built from that file.

Each folder has its own JSON file; a file not listed there is not used.

## What a file must be

- **Free of conditions.** In the public domain (or marked so with the Public
  Domain Mark), CC0, or under a licence that sets no condition at all, such
  as [Datenlizenz Deutschland Zero 2.0](https://www.govdata.de/dl-de/zero-2-0).
  Licences that require attribution (CC BY, Licence Ouverte, NLOD...) are not
  accepted, even though each file is credited anyway. One exception is made
  for the two KIT IFC files: their source says "for unrestricted use" in a
  notice, not a licence, and asks for a source credit in publications, which
  is given.
- **Clean.** No third-party logo or trademark in what it shows, nothing
  military or war-related, no nudity, and no person's name or local path in
  its metadata (author, last editor, file paths): they are blanked, and the
  credit says when a licence tag was removed.
- **Real.** Files as people actually make and receive them, with the
  complexity that comes with that (a designed PDF, a Word document with
  sections, tables and footnotes), not a scan or a file generated to look
  like one. Two exceptions are made here from the other files: the archives,
  to show nesting, and a simple slide deck, since no public-domain deck
  without third-party material turned up.
- **Small enough for a static site.** Under 15 MB each.
- **Named in 20 characters or fewer,** to fit the demo's sidebar.
- **Listed,** with where it comes from and why it may be used.

The archives and the deck made here from the other files are dedicated to
the public domain under CC0 1.0.

## samples.json

```json
{
  "samples": [
    {
      "file": "potsdam.dwg",
      "group": "cad",
      "credit": "Landeshauptstadt Potsdam, Stadtkarte mit ALKIS, tile 364_5808",
      "source": "https://opendata.potsdam.de/explore/dataset/stadtkarte-lika-potsdam-dwg/",
      "licence": "Datenlizenz Deutschland Zero 2.0 (dl-de/zero-2.0): any use, without conditions",
      "bytes": 1024156,
      "sha256": "…"
    }
  ]
}
```

| Field | |
|---|---|
| `file` | The file's name in the folder, shown as is in the sidebar |
| `group` | The sidebar section: `documents`, `images`, `cad`, `3d`, `media`, `archives`, or `unsupported` for files the viewer does not open (to show what it says about them) |
| `credit` | What it is and who made it, and what was changed |
| `source` | Where it was taken from |
| `licence` | Why it may be used |
| `bytes`, `sha256` | Checked when the files are copied into the demo |

## How exav uses it

exav's website workflow clones this repository's `HEAD` before it builds the
demo. Locally, in exav's `crates/exav-viewer`:

```sh
npm run demo:showcase                                 # from GitHub, HEAD
EXAV_SAMPLES=../../../exav-samples npm run demo:showcase   # from a local checkout
```

copies `viewer/` into `demo/public/showcase/` (not committed), checking each
file's size and hash against `samples.json`.

## Later

Other folders may follow, for exav's other tools: archives to extract, and
malware samples for the scanner. Malware will only ever be stored inside
password-protected ZIP files (password `infected`, the usual convention),
never as a plain file.

## The files

| File | From | Licence |
|---|---|---|
| `compton-paper.pdf` | Chang-Hao Fang et al., arXiv | CC0 1.0 |
| `usgs-fact-sheet.pdf` | U.S. Geological Survey | Public domain |
| `nps-report.docx` | U.S. National Park Service | Public domain |
| `demo-deck.pptx` | Made for the demo from the paintings and Potsdam's data | CC0 1.0 |
| `lassen-map.pdf` | U.S. National Park Service | Public domain |
| `energy-charts.xlsx` | U.S. Energy Information Administration | Public domain |
| `potsdam-streets.csv` | Landeshauptstadt Potsdam | dl-de/zero-2.0 |
| `kobke-osterbro.jpg` | Christen Købke, Statens Museum for Kunst | Public Domain Mark |
| `hammershoi.png` | Vilhelm Hammershøi, Statens Museum for Kunst | Public Domain Mark |
| `la-cour-beach.tif` | Janus la Cour, Statens Museum for Kunst | Public Domain Mark |
| `redon-orpheus.jp2` | Odilon Redon, Cleveland Museum of Art | CC0 1.0 |
| `potsdam.dwg` | Landeshauptstadt Potsdam | dl-de/zero-2.0 |
| `potsdam.dxf` | Landeshauptstadt Potsdam | dl-de/zero-2.0 |
| `kit-fzk-haus.ifc` | IAI / Karlsruhe Institute of Technology | "For unrestricted use", credit asked |
| `kit-smiley-west.ifc` | IAI / Karlsruhe Institute of Technology | "For unrestricted use", credit asked |
| `wild-boar.stl` | Statens Museum for Kunst, Royal Cast Collection | Public Domain Mark |
| `vieux-paris.mp4` | Musée départemental Albert-Kahn | CC0 1.0 |
| `folk-song-1957.wav` | Sveriges Radio, Statens musikverk | CC0 1.0 |
| `chopin-valse.mp3` | Musopen | CC0 1.0 |
| `nested.zip` | Made for the demo: a ZIP holding a 7z holding a tar.gz | CC0 1.0 |
| `eckersberg.jxl` (unsupported) | C.W. Eckersberg, Statens Museum for Kunst | Public Domain Mark |
| `streets.geojson` (unsupported) | Landeshauptstadt Potsdam | dl-de/zero-2.0 |

`viewer/samples.json` has the full credit and source of each.

## Licence

Each file keeps the licence listed for it. This README and the JSON files
are dedicated to the public domain under CC0 1.0.
