>[!definition] Transfer Learning
>Transfer Learning is a technique in machine learning in which knowledge learned from a task is reused on another task.

>[!definition] Fine-Tuning
>In deep learning, fine-tuning is an approach to transfer learning in which the weights of a pre-trained model are trained on new data. Fine-tuning can be done on the entire neural network, or on only a subset of  its layers, in which case the layers that are not being fine-tuned are "frozen" (not updated during the back propagation step).

<u><b>e.g.</b></u>  The following is an implementation in Python:
```Python
def train(model, data_loader, num_epochs=5, lr=0.001):
    device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
    model.to(device); model.train()
    criterion = nn.CrossEntropyLoss()
    optimizer = optim.Adam(model.parameters(), lr=lr)
    for epoch in range(num_epochs):
        model.train()
        running_loss = 0.0
        for i, (inputs, labels) in enumerate(data_loader):
            inputs, labels = inputs.to(device), labels.to(device)
            optimizer.zero_grad()
            outputs = model(inputs)
            loss = criterion(outputs, labels)
            loss.backward()
            optimizer.step()
            running_loss += loss.item()
            if i % 5 == 4:
                print(f'Epoch {epoch + 1}, Iteration {i + 1}, Loss: {running_loss / 5}')
                running_loss = 0.0
    print('Finished Training')
    
def test(model, data_loader):
    device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
    model.to(device); model.eval()
    correct = 0
    total = 0
    with torch.no_grad():
        for inputs, labels in data_loader:
            inputs, labels = inputs.to(device), labels.to(device)
            outputs = model(inputs)
            _, predicted = torch.max(outputs.data, 1)
            total += labels.size(0)
            correct += (predicted == labels).sum().item()
    print(f'Accuracy: {correct / total}')
```