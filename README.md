
## This is my personal implementation of using MetaSlot method on SAYCAM, a naturalistic egocentric dataset. This repo is adapted from [MetaSlot](https://github.com/lhj-lhj/MetaSlot)

## Modification compare to original Metaslot:

`\Config\config-metaslot\7-dinosaur-saycam-ViT_B16.py`: config file for metaslot-saycam experiment.

`\eminorhan`: To use pretrained model on saycam, adapted from [this](https://github.com/eminorhan/silicon-menagerie).

`\object_centric_bench\datum\dataset_saycam.py`

Also some modification in related files.

## Experimet

```bash
python train.py \
    --data_dir  DATA_DIR \
    --cfg_file ./Config/7-dinosaur-saycam-ViT_B16.py \
    --save_dir ./save \
    --use_dp"
```
Metaslot with `max_slot=7` on saycam, for 23 epochs. Experiment logs can be found in `/save/`.

Also I visulized the slots on some samples from SAYCAM_labled dataset, images can be found in `/visualize_frames`.

