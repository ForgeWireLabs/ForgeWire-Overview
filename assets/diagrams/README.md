# Diagram sources and exports

The `.mmd` files are the editable Mermaid sources. Matching `.svg` files are the responsive vector exports embedded in the public README; matching `.png` files are raster exports for previews and other platforms. The README captions identify each source.

To regenerate the exports with Node.js and npm:

```powershell
Get-ChildItem assets/diagrams -Filter *.mmd | ForEach-Object {
  npx --yes @mermaid-js/mermaid-cli@12.0.0 -i $_.FullName -o (Join-Path $_.DirectoryName ($_.BaseName + '.svg')) -b '#ffffff' -s 1.5
  if ($LASTEXITCODE -ne 0) { throw "SVG export failed: $($_.Name)" }
  npx --yes @mermaid-js/mermaid-cli@12.0.0 -i $_.FullName -o (Join-Path $_.DirectoryName ($_.BaseName + '.png')) -b '#ffffff' -s 2
  if ($LASTEXITCODE -ne 0) { throw "PNG export failed: $($_.Name)" }
}
```

Diagrams distinguish implementation paths from active work and intended behavior. Update their captions and status language when the implementation changes.
