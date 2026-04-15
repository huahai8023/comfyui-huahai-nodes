# comfyui-huahai-zip

This node saves connected ComfyUI images in order, renames the saved image files, and creates a zip file with a custom name.

## Usage

1. Connect the first image or image batch to `images`.
2. Connect extra images to `image_1`, `image_2`, ... in the order you want them saved.
3. Set `zip_name` for the zip file name.
4. Set `image_name_pattern` for the image base name or filename pattern.

Available `image_name_pattern` tokens:

- `{zip_name}`: final zip filename without `.zip`
- `{index}`: zero-padded image number
- `{number}`: image number without padding
- `{total}`: total image count

Default behavior: if `image_name_pattern` does not include `{number}` or `{index}`, the node automatically appends `_1`, `_2`, `_3`.

Examples:

- `zip_name = 三比四图压缩包`
- `image_name_pattern = 三比四图`
- Saved images: `三比四图_1.png`, `三比四图_2.png`, `三比四图_3.png`
- Zip file: `三比四图压缩包.zip`

If you still want leading zeros, use `{index}`. Example: `product_{index}` saves files like `product_001.png`, `product_002.png`.
