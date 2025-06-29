# email-spam-detection

### Purpose:
Counts how many times each word from a provided list appears in a given file (case-insensitive).

### How it works:

Initializes a dictionary with each word (in lowercase) from the provided list, setting the count to 0.
Tries to open the file. If the file doesn’t exist, prints an error and returns None.
Reads the file line by line, converts each line to lowercase, and splits it into words.
Increments the count in the dictionary for each occurrence of the target words.
Returns the dictionary of word counts.

### Example usage:

Counts occurrences of "lottery", "now", and "free" in "spam_email.txt".
Prints the count for each word found.

### Sample Output:
If "lottery" appears 2 times, "now" 1 time, and "free" 4 times, the output would be:

```
'lottery' appears 2 times.
'now' appears 1 times.
'free' appears 4 times.
```

### Error Handling:
If the file doesn’t exist, it prints an error and returns None.

---
🧠 Spam Detector Summary
# 1. 📦 Imports
* **torch:** Core PyTorch library.
* **torch.nn:** Neural network building blocks.
* **torch.nn.functional:** Activation functions like ReLU and sigmoid.

# 2. 📨 Input Vector

``` python
result = {'lottery': 1, 'now': 0, 'free': 1}
x = torch.tensor([list(result.values())], dtype=torch.float32)  # shape: (1, 3)
```

* Converts word presence into a 2D tensor.
* dtype=torch.float32 ensures compatibility with model weights.

# 3. 🏗️ Neural Network Definition

``` python
class SpamDetector(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc1 = nn.Linear(3, 4)
        self.fc2 = nn.Linear(4, 1)

    def forward(self, x):
        x = F.relu(self.fc1(x))
        return torch.sigmoid(self.fc2(x))
```
* **fc1:** Input (3 features) → Hidden (4 neurons).

* **fc2:** Hidden → Output (1 neuron).

* **ReLU:** Adds non-linearity.

* **Sigmoid:** Outputs probability between 0 and 1.

# 4. 🚀 Model Execution

``` python
model = SpamDetector()
output = model(x)
print(f"Spam probability: {output.item():.4f}")
```
* Runs the input through the model.

* Prints the spam probability (e.g., 0.7412).
