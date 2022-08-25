# Genre-Specific Music Generation Using RNN-LSTM With Magenta

The project is an application of Deep Learning model RNN-LSTM which is used to generate continuous sequences learned from previous sequences. The model is implemented in music in midi format which provides sequences as notes and as a result future notes are predicted in order to create a new set of music which contaons the essence of that specoific genre by or LSTM trained model. The model is trained for each genre of the music and was able to generate music resembling that particular genre it was trained on. 
With the ability to generate melodies based on a specific genre, a personalized music can be generated for each person based on their data about their genre preference.

## Getting Started

### Installing Magenta
[Magenta](https://github.com/piyusharma4/magenta) is a research project exploring the role of machine learning in the process of creating art and music. Primarily this involves developing new deep learning and reinforcement learning algorithms for generating songs, images, drawings, and other materials.
#### Manual Install (w/o Anaconda)

If the automated script fails for any reason, or you'd prefer to install by
hand, do the following steps.

Install the Magenta pip package:

```bash
pip install magenta
```

**NOTE**: In order to install the `rtmidi` package that we depend on, you may need to install headers for some sound libraries. On Linux, this command should install the necessary packages:

```bash
sudo apt-get install build-essential libasound2-dev libjack-dev
```

The Magenta libraries are now available for use within Python programs and
Jupyter notebooks, and the Magenta scripts are installed in your path!

#### GPU Installation

If you have a GPU installed and you want Magenta to use it, you will need to
follow the [Manual Install](#manual-install) instructions, but with a few
modifications.

First, make sure your system meets the [requirements to run tensorflow with GPU support](
https://www.tensorflow.org/install/install_linux#nvidia_requirements_to_run_tensorflow_with_gpu_support).

Next, follow the [Manual Install](#manual-install) instructions, but install the
`magenta-gpu` package instead of the `magenta` package:

```bash
pip install magenta-gpu
```

The only difference between the two packages is that `magenta-gpu` depends on
`tensorflow-gpu` instead of `tensorflow`.

Magenta should now have access to your GPU.


### Installing essential libraries and packages
Open a new terminal window so the environmental variable changes take effect and enter:

```sh
source activate magenta && pip install tensorflow-gpu &&
git clone https://github.com/piyusharma4/genre-melodies.git &&
cd genre-melodies &&
pip install -r requirements.txt &&
python create_dataset.py &&
sh train_model.sh
```

If using a CPU replace 'tensorflow-gpu' with 'tensorflow'.


## Preprocessing and Analysis

See the [preprocessing and visualization notebook](/create_dataset.ipynb) for sample outputs and visualization scripts.

Visualizations:

![2d visualization](/images/2d-genre-visualization.png)

![3d visualization](/images/3d-genre-visualization.png)

Tensorboard graph of trained network:

[<img src="/images/magenta_graph.png" alt="Tensorboard Graph" width="60%"/>](/images/magenta_graph.png)

## Output

Each genre folder created contains 10 generated melodies for each particular genre. NOTE: Each generated music has asme MIDI note C5 (can be changed as a hyperparameter).

Check out some [samples](https://drive.google.com/drive/folders/19pwp-DUN9R0xu4b1QlJX-rHCIM3CwiIc?usp=sharing) using Melody_RNN which gives better sweet sounding results for most of the genres.

We can generate music using Improv_RNN by Magenta to further use a specific combination of chords, just change the configuration to chord_pitches_improv.

Some generated music using chords are uploaded in [SoundCloud](https://soundcloud.com/piyush-sharma-542285406). <---Check this one, I've named them according to my what my mood said while listening to them.

I've also included some of generated music using different model type implementation like Chords_Pitches_RNN,Polyphonic_RNN which can be found in above Chord_Pitches_RNN_Results and Polyphonic_RNN_Results folder respectively.
