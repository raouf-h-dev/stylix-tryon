# GLB Clothing Files

Place your GLB files here with EXACTLY these names:

  shirt.glb   ← your shirt 3D model
  pants.glb   ← your pants 3D model

## Why StreamingAssets?

StreamingAssets is the correct folder for GLTFast local loading on iOS because:
- Files are copied AS-IS into the iOS .app bundle (no compression/processing)
- Accessible at runtime via Application.streamingAssetsPath (a real file:// path on iOS)
- GLTFast's GltfImport.Load(uri) works with file:// URIs pointing here
- No Resources.Load() limitations (no 4 GB limit, supports binary .glb)

## Alternative: Resources folder

Would require renaming to .bytes extension and using Resources.Load<TextAsset>()
then passing bytes to GltfImport.LoadGltfBinary() — more complex, not recommended.

## File naming

The names are configured in the GLBLocalLoader component Inspector:
  - Shirt File Name: shirt.glb
  - Pants File Name: pants.glb

You can rename them in the Inspector without touching code.
