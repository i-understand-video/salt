# Segment Anything Labelling Tool (SALT)

Uses the Segment-Anything Model By Meta AI and adds a barebones interface to label images and saves the masks in the COCO format.

Under active development, apologies for rough edges and bugs. Use at your own risk.

## Installation and usage

1. Create a virtual environment (`python3 -mvenv salt`)
2. `pip install -r requirments.txt`
3. Download model from [Segment Anything](https://github.com/facebookresearch/segment-anything) on any machine with a GPU
4. Stash dataset in the following format `<dataset_name>/images/*` and create empty folder `<dataset_name>/embeddings`.
    - Annotations will be saved in `<dataset_name>/annotations.json` by default
5. examine and/or call the bash scripts `generate_embeddings.sh` and `generate_onnx.sh`
6. (Optional) Install [coco-viewer](https://github.com/trsvchn/coco-viewer) to scroll through your annotations quickly.
7. Call `segment_anything_annotator.py` in the same manner as the following `python segment_anything_annotator.py --dataset-path pictures --categories in,out`.
    - There are a few keybindings that make the annotation process fast.
    - Click on the object using left clicks and right click (to indicate outside object boundary).
    - `n` adds predicted mask into your annotations. (Add button)
    - `r` rejects the predicted mask. (Reject button)
    - `a` and `d` to cycle through images in your your set. (Next and Prev)
    - `l` and `k` to increase and decrease the transparency of the other annotations.
    - `Ctrl + S` to save progress to the COCO-style annotations file.
8. [coco-viewer](https://github.com/trsvchn/coco-viewer) to view your annotations.
    - `python cocoviewer.py -i <dataset> -a <dataset>/annotations.json`

## Demo

![How it Works Gif!](https://github.com/anuragxel/salt/raw/main/assets/how-it-works.gif)

## Contributing

Please contribute to the main repo this is forked from 

## License

The code is licensed under the MIT License. By contributing to SALT, you agree to license your contributions under the same license as the project. See LICENSE for more information.
