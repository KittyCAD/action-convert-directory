# Convert all files in a directory

This action will convert all 3D files in a directory to your desired format.
You will need to generate a `KITTYCAD_API_TOKEN` [here](https://kittycad.io/account) and add it to your repo's secrets

Example usage:
```yml
name: Convert files
on:
    pull_request:
jobs:
  test-convert-directory-action:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: KittyCAD/action-convert-directory@v0.0.2
        with:
          kittycad-token: ${{ secrets.KITTYCAD_API_TOKEN }}
          input-directory: original-files-path
          output-directory: converted-files-path
          conversion-type: fbx
      - name: Check files converted
        run: ls converted-files-path # prints converted file names
```

Be sure to look at our [other Github Actions](https://github.com/marketplace?type=actions&query=kittycad+).
