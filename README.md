# convert all files in a directory

This action will convert all 3D files in a directory to your desired format.

```yml
name: "test converting files"
on:
    pull_request:
jobs:
  test-convert-directory-action:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: KittyCAD/ts-actions/convert-dir@v0.2.2
        with:
          kittycad-token: ${{ secrets.KITTYCAD_API_TOKEN }}
          input-directory: original-files-path
          output-directory: converted-files-path
          conversion-type: fbx
      - name: Check files converted
        run: ls converted-files-path # prints converted file names
```