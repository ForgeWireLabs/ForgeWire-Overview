# Diagram sources and exports

The `.mmd` files are the editable Mermaid sources. Matching `.png` files are embedded in the public README; matching `.svg` files are linked beside each image for zoomable vector viewing. Each diagram uses the same status key: existing, optional/configuration-dependent, private implementation, and proposed or in-progress behavior.

To regenerate the exports with Node.js and npm:

```powershell
Get-ChildItem assets/diagrams -Filter *.mmd | ForEach-Object {
  npx --yes @mermaid-js/mermaid-cli@12.0.0 -i $_.FullName -o (Join-Path $_.DirectoryName ($_.BaseName + '.svg')) -b '#ffffff' -s 1.5
  if ($LASTEXITCODE -ne 0) { throw "SVG export failed: $($_.Name)" }
  npx --yes @mermaid-js/mermaid-cli@12.0.0 -i $_.FullName -o (Join-Path $_.DirectoryName ($_.BaseName + '.png')) -b '#ffffff' -s 2
  if ($LASTEXITCODE -ne 0) { throw "PNG export failed: $($_.Name)" }
}
```

Diagrams distinguish implementation paths from active work and intended behavior. Update their captions and status language when the implementation changes. The exports should be regenerated together whenever a `.mmd` source changes.
