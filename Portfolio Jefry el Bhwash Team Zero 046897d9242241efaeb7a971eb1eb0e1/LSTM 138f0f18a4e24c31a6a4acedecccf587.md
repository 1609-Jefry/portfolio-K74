# LSTM

[W15_LSTMConsumptionSimpleV13.pdf](LSTM%20138f0f18a4e24c31a6a4acedecccf587/W15_LSTMConsumptionSimpleV13.pdf)

## Choice of this model:

LSTM: Long Short-Term Memory

An LSTM is a form of a recurrent Neural Network. Multiple papers during the research pointed to different forms of this network. The reason a lot of people think this should work is because an LSTM tries to create a hidden representation of the dataset which is forgotten after some arbitrary time frame.
The consumption will have some pattern in it over the long term and short term, these patterns change. Therefore an LSTM fulfils the function of predicting energy consumption very well.

![https://upload.wikimedia.org/wikipedia/commons/3/3b/The_LSTM_cell.png](https://upload.wikimedia.org/wikipedia/commons/3/3b/The_LSTM_cell.png)

stolen image from the internet

## Application

The dataset read through a pickle which was created using the notebook in DataPreprocessing&Analysis

- The Dataset is split before anything is done with it

![LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled.png](LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled.png)

- After that the split the Train, Validate and Test data were separately scaled to prevent any data-leaks.

The scaled datasets were processed using a moving window while changing it to three dimensional matrixes.

```python
def dim3(dft, window=7, gap=24):
    #Get time shifted values and apply a moving window
    X = np.concatenate([ dft[i:i+window].to_numpy().reshape(1, window, dft.shape[1]) for i in range(len(dft)-window-gap) ], axis=0)
    
    #Get the target value (which is the next one in the sequence)
    y = dft.to_numpy()[window + gap:, -1]    
    print(f"X_shape: {X.shape}")
    print(f"y_shape: {y.shape}")
    return X.astype(np.float32), y.astype(np.float32)
```

The simplest form of the LSTM with the addition of making the output stationairy is being used here:

```python
class lstm(nn.Module):
    def __init__(self, feature_size=1, hidden_state_size = 100):
        super().__init__()
        self.hidden_state_size = hidden_state_size
        self.lstm1 = nn.LSTM(feature_size, self.hidden_state_size, batch_first=True)
        self.linear2 = nn.Linear(self.hidden_state_size, 1)
        
    def forward(self, X): #tensor X
        h, _ = self.lstm1( X )          # h shaped (batch, sequence, hidden_layer)
        h = h[:,-1, :]                  # only need the output for the last sequence

        y = self.linear2(h)             # make a prediction
        if stationary:
            y = y + X[:,-1,-1:]         # make the output stationary
        return y.view(-1)               # like always
```

## Training

![LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%201.png](LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%201.png)

Epoch: 1

![LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%202.png](LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%202.png)

Epoch: 1500

![LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%203.png](LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%203.png)

From the loss graph the minimum was reached around epoch 50, then it went up and the model was **overfitting.** 

![LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%204.png](LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%204.png)

Using the naked eye, even when overfit this seems like it's a decent prediction.

In later stages the epoch count was set to a lower value around 50.

![LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%205.png](LSTM%20138f0f18a4e24c31a6a4acedecccf587/Untitled%205.png)

The model output and the target variable are not linear at all, but there have been worse exaples before this graph.