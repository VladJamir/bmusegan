# BinaryMuseGAN

[BinaryMuseGAN](https://salu133445.github.io/bmusegan/) is a follow-up project
of the [MuseGAN](https://salu133445.github.io/musegan/) project.

In this project, we first investigate how the real-valued piano-rolls generated
by the generator may lead to difficulties in training the discriminator for
CNN-based models. To overcome the binarization issue, we propose to append to
the generator an additional refiner network, which try to refine the real-valued
predictions generated by the pretrained generator to binary-valued ones. The
proposed model is able to directly generate binary-valued piano-rolls at test
time.

We trained the network with
[Lakh Pianoroll Dataset](https://salu133445.github.io/lakh-pianoroll-dataset/)
(LPD). We use the model to generate four-bar musical phrases consisting of eight
tracks: *Drums*, *Piano*, *Guitar*, *Bass*, *Ensemble*, *Reed*, *Synth Lead* and
*Synth Pad*. Audio samples are available
[here](https://salu133445.github.io/bmusegan/samples).

## Run the code

### Configuration

Modify `config.py` for configuration.

- Quick setup

  Change the values in the dictionary `SETUP` for a quick setup. Documentation
  is provided right after each key.

- More configuration options

  Three dictionaries `EXP_CONFIG`, `MODEL_CONFIG` and `TRAIN_CONFIG` define configuration variables in experiment, model and training levels,
  respectively.

  > The automatically-determined experiment name is based only on the values
defined in the dictionary `SETUP`, so remember to provide the experiment name
manually (so that you won't overwrite a trained model).

### Run

```bash
python main.py
```

## Training Data

- Prepare your own data

  The array will be reshaped to (-1, `num_bar`, `num_timestep`, `num_pitch`,
  `num_track`). These variables are defined in `config.py`.

- Download our training data [here](https://salu133445.github.io/bmusegan/data).
