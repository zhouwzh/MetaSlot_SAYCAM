
## This is my personal implementation of using MetaSlot method on SAYCAM, a naturalistic egocentric dataset. This repo is adapted from [MetaSlot](https://github.com/lhj-lhj/MetaSlot)

## Modification compare to original Metaslot:

`\Config\config-metaslot\7-dinosaur-saycam-ViT_B16.py`: config file for metaslot-saycam experiment.

`\eminorhan`: To use pretrained model on saycam, adapted from [this](https://github.com/eminorhan/silicon-menagerie).

`\object_centric_bench\datum\dataset_saycam.py`

Also some modifications in related files.

## Experimet

Metaslot with `max_slot=7` on saycam, for 23 epochs. Experiment logs can be found in `/save/`.

```bash
python train.py \
    --data_dir  DATA_DIR \
    --cfg_file ./Config/7-dinosaur-saycam-ViT_B16.py \
    --save_dir ./save \
    --use_dp"
```

Also I visulized the slots on some samples from SAYCAM_labled dataset, images can be found in `/visualize_frames`.

```bash
python train.py \
    --data_dir  / \
    --cfg_file ./save/dinosaur-saycam-ViT_B16/max_slot-7/7-dinosaur-saycam-ViT_B16.py \
    --ckpt_file ./save/7-dinosaur-saycam-ViT_B16/42_20251023_235721/checkpoint.pth.tar \
    --save_dir ./save \
    --use_dp \
    --dev \
    --visualize
```

## Current porblems

1. Visuliaztion could be worse when using larger max_slots.
2. The visulization of slots not quite capture the specific objects in some samples.
