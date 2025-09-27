# 🎵 AI-Powered Melody Generation using RNN-LSTM

A sophisticated machine learning project that generates original musical melodies using Recurrent Neural Networks (LSTM). This project demonstrates advanced deep learning techniques applied to music composition, featuring both a Streamlit web interface and command-line tools.

## 🌟 Project Overview

This project implements an end-to-end melody generation system that:
- **Processes 1,700+ German folk songs** from the KernScores dataset
- **Trains a custom LSTM neural network** to learn musical patterns and structures
- **Generates original melodies** based on user input or seed sequences
- **Provides multiple interfaces** (Streamlit web app, command-line tool)
- **Exports compositions** in MIDI format for playback and further editing

## 🚀 Key Features

### 🎼 Advanced Music Processing
- **Intelligent Data Preprocessing**: Converts KernScores (.krn) files to standardized MIDI format
- **Musical Transposition**: Automatically transposes all songs to C major or A minor for consistency
- **Duration Filtering**: Only processes songs with standard musical durations (quarter notes, half notes, etc.)
- **Time Series Encoding**: Converts musical notes into numerical sequences for neural network training

### 🧠 Deep Learning Architecture
- **LSTM Neural Network**: 256-unit LSTM layer with dropout regularization
- **Custom Implementation**: Handles deprecated TensorFlow parameters for compatibility
- **Temperature Sampling**: Controls creativity vs. predictability in generated melodies
- **Sequence-to-Sequence Learning**: Learns from 64-note sequences to predict next notes

### 🎹 Multiple User Interfaces
- **Streamlit Web App**: Interactive web interface with real-time music generation
- **Command-Line Tool**: Python script for batch processing and automation
- **MuseScore Integration**: Automatic sheet music visualization

## 📊 Technical Specifications

### Dataset
- **Source**: KernScores German folk song collection
- **Size**: 1,700+ individual songs
- **Format**: KernScores (.krn) → MIDI → Encoded sequences
- **Vocabulary**: 38 unique symbols (notes, rests, extensions)

### Model Architecture
```
Input Layer: (None, None, 38) - One-hot encoded sequences
LSTM Layer: 256 units with dropout (0.2)
Dense Layer: 38 units with softmax activation
Total Parameters: 311,846 trainable parameters
```

### Training Configuration
- **Epochs**: 50
- **Batch Size**: 64
- **Learning Rate**: 0.001
- **Optimizer**: Adam
- **Loss Function**: Sparse Categorical Crossentropy
- **Final Accuracy**: ~85%+

## 🛠️ Installation & Setup

### Prerequisites
```bash
pip install tensorflow keras music21 streamlit numpy
```

### Required Software
- **Python 3.7+**
- **MuseScore 4** (for sheet music visualization)
- **MIDI Player** (for audio playback)

### Quick Start
1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Melody-Generation-using-RNN-LSTM
   ```

2. **Run the Streamlit web app**
   ```bash
   streamlit run app.py
   ```

3. **Or use the command-line interface**
   ```bash
   python text_to_music_generator.py
   ```

## 📁 Project Structure

```
Melody-Generation-using-RNN-LSTM/
├── app.py                          # Streamlit web application
├── text_to_music_generator.py      # Command-line interface
├── data_preprocessing.ipynb        # Data preprocessing pipeline
├── generator.ipynb                 # Model training and generation
├── test.ipynb                      # Model training script
├── mapping.json                    # Note-to-integer mapping
├── file_dataset                    # Processed training data
├── model_fixed.h5                  # Trained LSTM model
├── dataset/                        # Individual processed songs
├── deutschl/                       # Original KernScores dataset
│   ├── erk/                        # Main folk song collection
│   ├── ballad/                     # Ballad collection
│   └── ...                         # Additional collections
└── mel.mid                         # Generated melody output
```

## 🎵 Usage Examples

### Web Interface (Streamlit)
1. Launch the app: `streamlit run app.py`
2. Enter MIDI values in the text input (e.g., "60 62 64 65")
3. Click "Generate Music" to create a new melody
4. Click "View Sheet Music" to open in MuseScore

### Command Line Interface
```bash
python text_to_music_generator.py
# Enter MIDI sequence: 60 62 64 65
# Generated melody saved as 'mel.mid'
```

### Example Input Formats
- **Ascending Scale**: `60 62 64 65 67 69 71 72`
- **Repeated Notes**: `67 _ 67 _ 67 _ _ 65`
- **Descending Scale**: `72 71 69 67 65 64 62 60`
- **Arpeggio Pattern**: `60 _ _ 64 _ _ 67 _ _`
- **With Rests**: `r _ _ 60 62 64`

## 🔬 Technical Implementation

### Data Preprocessing Pipeline
1. **File Loading**: Recursively loads all .krn files from the dataset
2. **Duration Filtering**: Removes songs with non-standard note durations
3. **Key Transposition**: Transposes all songs to C major or A minor
4. **MIDI Encoding**: Converts musical notes to MIDI values
5. **Sequence Creation**: Generates training sequences with proper delimiters

### Model Training Process
1. **Sequence Generation**: Creates 64-note input sequences with corresponding targets
2. **One-Hot Encoding**: Converts integer sequences to categorical format
3. **LSTM Training**: Trains the model to predict next notes in sequences
4. **Model Persistence**: Saves trained model for future use

### Generation Algorithm
1. **Seed Processing**: Takes user input and creates initial sequence
2. **Iterative Prediction**: Uses LSTM to predict next note probabilities
3. **Temperature Sampling**: Applies temperature scaling for controlled randomness
4. **MIDI Conversion**: Converts generated sequence back to MIDI format

## 📈 Performance Metrics

- **Training Accuracy**: 85%+ after 50 epochs
- **Model Size**: 311,846 parameters
- **Generation Speed**: ~40ms per note prediction
- **Dataset Coverage**: 1,700+ songs processed
- **Vocabulary Size**: 38 unique musical symbols

## 🎯 Key Achievements

### Technical Excellence
- **Custom LSTM Implementation**: Handles TensorFlow compatibility issues
- **Robust Data Pipeline**: Processes diverse musical formats and structures
- **Multiple Interfaces**: Both web and command-line access
- **Production Ready**: Error handling and user-friendly interfaces

### Musical Intelligence
- **Pattern Recognition**: Learns complex musical relationships and progressions
- **Creative Generation**: Produces original melodies with musical coherence
- **Flexible Input**: Accepts various input formats and seed sequences
- **Professional Output**: Generates standard MIDI files for further use

## 🔮 Future Enhancements

- **Multi-track Generation**: Support for harmony and accompaniment
- **Style Transfer**: Generate melodies in different musical styles
- **Real-time Generation**: Live music generation during performance
- **Advanced Architectures**: Transformer-based models for improved quality
- **Web Deployment**: Cloud deployment for public access

## 🛡️ Error Handling

The project includes comprehensive error handling for:
- Invalid MIDI input sequences
- Missing model files
- MuseScore installation issues
- File I/O operations
- TensorFlow compatibility problems

## 📚 Dependencies

- **TensorFlow/Keras**: Deep learning framework
- **Music21**: Music analysis and processing
- **Streamlit**: Web application framework
- **NumPy**: Numerical computing
- **JSON**: Data serialization

## 🤝 Contributing

This project demonstrates advanced machine learning techniques in music generation. Contributions are welcome for:
- Model architecture improvements
- Additional musical features
- User interface enhancements
- Performance optimizations

## 📄 License

This project is for educational and research purposes. Please ensure proper attribution when using the code or generated melodies.

---

**Built with ❤️ using Python, TensorFlow, and Music21**

*This project showcases the intersection of artificial intelligence and music composition, demonstrating practical applications of deep learning in creative domains.*
