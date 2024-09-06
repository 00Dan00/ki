- scypy, matplotlib, pandas basics down
- tensorflow / pytorch course
- q learning
- algorithms
- basic mathematics (integration, statistics)
- bachelor thema


Plan für morgen:
clustering. K-means, k-shift
huber loss, comparison of regression error functions
classification error functions


https://universe.roboflow.com/browse/self-driving

### 2. Training Neural Networks




**Optimization Algorithms**:
- **Stochastic Gradient Descent (SGD)**: Updates weights using one or a few training examples at each step.
- **Adam**: An adaptive learning rate optimization algorithm that combines the advantages of two other extensions of stochastic gradient descent: AdaGrad and RMSProp.

### 3. Model Architecture
**Types of Neural Networks**:
- **Feedforward Neural Networks (FNN)**: The simplest type where connections do not form cycles. Often used for basic classification and regression tasks.
- **Convolutional Neural Networks (CNN)**: Specialized for processing grid-like data such as images. Uses convolutional layers to automatically and adaptively learn spatial hierarchies of features.
- **Recurrent Neural Networks (RNN)**: Designed for sequential data, useful in time series and natural language processing (NLP). Variants include LSTM (Long Short-Term Memory) and GRU (Gated Recurrent Unit).
- **Transformers**: Modern architectures, especially in NLP tasks, which use self-attention mechanisms to process data in parallel, unlike RNNs.

**Hyperparameters**:
- **Learning Rate**: Controls how much to change the model in response to the estimated error each time the model weights are updated.
- **Batch Size**: The number of training examples utilized in one iteration.
- **Number of Layers and Neurons**: The depth and width of the neural network, respectively.

### 4. Regularization Techniques
**Overfitting and Underfitting**:
- **Overfitting**: When a model learns the training data too well, including its noise, and performs poorly on new data.
- **Underfitting**: When a model is too simple to capture the underlying patterns in the data.

**Dropout**:
- A regularization technique where randomly selected neurons are ignored during training to prevent overfitting.

**L1 and L2 Regularization**:
- **L1 Regularization (Lasso)**: Adds the absolute value of the magnitude of the coefficient as a penalty term to the loss function.
  \[ \text{L1 penalty} = \lambda \sum_{j=1}^{p} |w_j| \]
- **L2 Regularization (Ridge)**: Adds the squared magnitude of the coefficient as a penalty term to the loss function.
  \[ \text{L2 penalty} = \lambda \sum_{j=1}^{p} w_j^2 \]

### 5. Data Preparation and Augmentation
**Data Preprocessing**:
- **Normalization**: Scaling input features to have zero mean and unit variance.
- **Standardization**: Scaling features to lie within a fixed range, typically [0, 1].

**Data Augmentation**:
- Techniques to artificially increase the size of the training dataset by creating modified versions of data, such as rotating, flipping, or cropping images.

### 6. Evaluation Metrics
**Classification Metrics**:
- **Accuracy**: The ratio of correctly predicted instances to the total instances.
- **Precision**: The ratio of true positive predictions to the total predicted positives.
- **Recall**: The ratio of true positive predictions to the total actual positives.
- **F1 Score**: The harmonic mean of precision and recall.
- **ROC-AUC**: A performance measurement for classification problems at various threshold settings.

**Regression Metrics**:
- **Mean Absolute Error (MAE)**: The average of the absolute errors.
- **Mean Squared Error (MSE)**: The average of the squared errors.
- **R-squared**: The proportion of the variance in the dependent variable that is predictable from the independent variables.

### 7. Advanced Topics
**Transfer Learning**:
- Using a pre-trained model on a new but related task. The pre-trained model provides a good starting point, especially when data is limited.

**Fine-Tuning**:
- Adjusting a pre-trained model on a new dataset, often by retraining some layers of the network.

**Unsupervised Learning**:
- Techniques like autoencoders (for data compression and reconstruction) and GANs (for generating new, synthetic instances of data).

### 8. Practical Implementation
**Frameworks**:
- **TensorFlow**: A powerful, flexible open-source library for deep learning developed by Google.
- **Keras**: A high-level API for building and training deep learning models, running on top of TensorFlow.
- **PyTorch**: An open-source deep learning platform that provides a seamless path from research prototyping to production deployment.

**Model Deployment**:
- Ensuring models are efficient and scalable in production environments.
- Techniques include optimizing model size and inference speed.

### 9. Ethical Considerations
**Bias and Fairness**:
- Ensuring models do not perpetuate or amplify biases present in the training data.

**Privacy**:
- Techniques like differential privacy to ensure the privacy of data used in training models.

**Explainability**:
- Methods to make the decisions of deep learning models interpretable, such as LIME or SHAP.

### 10. Continuous Learning and Experimentation
**Experiment Tracking**:
- Tools to track different experiments, their configurations, and results to manage and reproduce experiments.

**Hyperparameter Tuning**:
- Techniques such as grid search, random search, and Bayesian optimization for tuning hyperparameters to find the best model configuration.

### Summary
Deep learning is a comprehensive and rapidly evolving field requiring a solid grasp of neural network principles, training processes, model architectures, data handling, evaluation metrics, advanced techniques, practical implementation, and ethical considerations. Staying current with the latest research and methodologies is crucial for success in this domain.






!!!!!!!!!!!!

Writing a bachelor's thesis on AI in autonomous driving with a focus on reinforcement learning (RL) and CARLA, a popular open-source simulator, is an excellent choice. Here's a suggestion for a thesis title and a potential focus area:

### Thesis Title

**"Enhancing Autonomous Driving Policies with Reinforcement Learning in CARLA: A Comprehensive Evaluation"**

### Focus Areas

To create a well-rounded thesis, consider focusing on the following areas:

1. **Introduction to Autonomous Driving and AI**:
    
    - Discuss the importance of AI in autonomous vehicles.
    - Highlight the role of reinforcement learning in decision-making and policy learning.
2. **Reinforcement Learning Basics**:
    
    - Explain the fundamentals of reinforcement learning, including key concepts such as agents, environments, states, actions, rewards, and policies.
    - Discuss different RL algorithms like Q-Learning, Deep Q-Networks (DQN), and Policy Gradient Methods.
3. **Overview of CARLA Simulator**:
    
    - Introduce CARLA as a tool for simulating urban driving environments.
    - Discuss its features, capabilities, and why it is useful for RL research in autonomous driving.
4. **Designing Reinforcement Learning Experiments**:
    
    - Outline the experimental setup in CARLA.
    - Describe how you will design RL experiments, including the definition of the environment, state space, action space, and reward function.
5. **Implementing Reinforcement Learning Algorithms**:
    
    - Choose one or more RL algorithms to implement within the CARLA environment.
    - Discuss the implementation details, challenges, and any modifications made to suit the driving context.
6. **Evaluation and Analysis**:
    
    - Evaluate the performance of the RL-based autonomous driving system using metrics such as safety, efficiency, and comfort.
    - Compare the results with baseline approaches or other RL methods.
7. **Challenges and Limitations**:
    
    - Discuss the challenges faced during the research, such as sample efficiency, exploration-exploitation trade-off, and generalization to different scenarios.
    - Analyze the limitations of the current RL methods in autonomous driving.
8. **Future Directions**:
    
    - Suggest possible improvements and future research directions, such as incorporating other AI techniques or enhancing RL algorithms for better performance.
9. **Conclusion**:
    
    - Summarize the key findings and contributions of your research.
    - Reflect on the potential impact of RL in the development of autonomous driving technologies.

### Practical Considerations

- **Scope and Depth**: Ensure the scope of your thesis is manageable within the page limit and your available time. Focus on a specific aspect of RL and autonomous driving to provide depth rather than breadth.
    
- **Simulation Scenarios**: Create diverse driving scenarios in CARLA to test your RL algorithms, such as urban environments, highways, and intersections.
    
- **Baseline Comparison**: Consider comparing your RL approach with traditional rule-based systems or other machine learning techniques to highlight its strengths and weaknesses.
    
- **Software and Tools**: Make use of Python, PyTorch, or TensorFlow for implementing RL algorithms, as well as CARLA's Python API for integrating your models with the simulator.
    

By focusing on these areas, you can create a comprehensive and insightful thesis that explores the application of reinforcement learning in autonomous driving using the CARLA simulator. Let me know if you need further guidance or specific details on any section!




!!!!!!!!!!!!!

### Titel der Abschlussarbeit

**"Verbesserung von Fahrstrategien im autonomen Fahren durch Reinforcement Learning in CARLA: Eine umfassende Evaluierung"**

### Fokussierte Themenbereiche

Um eine gut strukturierte Abschlussarbeit zu erstellen, sollten Sie sich auf die folgenden Bereiche konzentrieren:

1. **Einführung in autonomes Fahren und KI**:
    
    - Diskutieren Sie die Bedeutung von KI in autonomen Fahrzeugen.
    - Heben Sie die Rolle von Reinforcement Learning bei der Entscheidungsfindung und Strategieentwicklung hervor.
2. **Grundlagen des Reinforcement Learning**:
    
    - Erklären Sie die Grundlagen des Reinforcement Learning, einschließlich Schlüsselkonzepte wie Agenten, Umgebungen, Zustände, Aktionen, Belohnungen und Strategien.
    - Diskutieren Sie verschiedene RL-Algorithmen wie Q-Learning, Deep Q-Networks (DQN) und Policy-Gradient-Methoden.
3. **Überblick über den CARLA-Simulator**:
    
    - Stellen Sie CARLA als Werkzeug zur Simulation urbaner Fahrumgebungen vor.
    - Diskutieren Sie dessen Merkmale, Fähigkeiten und warum es nützlich für RL-Forschung im autonomen Fahren ist.
4. **Entwurf von Reinforcement Learning Experimenten**:
    
    - Skizzieren Sie den experimentellen Aufbau in CARLA.
    - Beschreiben Sie, wie Sie RL-Experimente entwerfen, einschließlich der Definition der Umgebung, des Zustandsraums, des Aktionsraums und der Belohnungsfunktion.
5. **Implementierung von Reinforcement Learning Algorithmen**:
    
    - Wählen Sie einen oder mehrere RL-Algorithmen zur Implementierung innerhalb der CARLA-Umgebung.
    - Diskutieren Sie die Implementierungsdetails, Herausforderungen und eventuelle Anpassungen an den Fahrkontext.
6. **Evaluierung und Analyse**:
    
    - Bewerten Sie die Leistung des RL-basierten autonomen Fahrsystems anhand von Kennzahlen wie Sicherheit, Effizienz und Komfort.
    - Vergleichen Sie die Ergebnisse mit Basisansätzen oder anderen RL-Methoden.
7. **Herausforderungen und Einschränkungen**:
    
    - Diskutieren Sie die Herausforderungen, denen Sie während der Forschung begegnet sind, wie z.B. Effizienz bei der Stichprobenziehung, Abwägung zwischen Erkundung und Ausnutzung und Generalisierung auf verschiedene Szenarien.
    - Analysieren Sie die Einschränkungen der aktuellen RL-Methoden im autonomen Fahren.
8. **Zukünftige Richtungen**:
    
    - Schlagen Sie mögliche Verbesserungen und zukünftige Forschungsrichtungen vor, wie z.B. die Integration anderer KI-Techniken oder die Verbesserung von RL-Algorithmen für bessere Leistung.
9. **Fazit**:
    
    - Fassen Sie die wichtigsten Erkenntnisse und Beiträge Ihrer Forschung zusammen.
    - Reflektieren Sie über das potenzielle Einfluss von RL auf die Entwicklung von Technologien im autonomen Fahren.

### Praktische Überlegungen

- **Umfang und Tiefe**: Stellen Sie sicher, dass der Umfang Ihrer Arbeit im Rahmen der Seitenbegrenzung und Ihrer verfügbaren Zeit machbar ist. Konzentrieren Sie sich auf einen spezifischen Aspekt von RL und autonomem Fahren, um Tiefe anstelle von Breite zu bieten.
    
- **Simulationsszenarien**: Erstellen Sie vielfältige Fahrszenarien in CARLA, um Ihre RL-Algorithmen zu testen, z.B. urbane Umgebungen, Autobahnen und Kreuzungen.
    
- **Vergleich mit Baselines**: Ziehen Sie einen Vergleich Ihres RL-Ansatzes mit traditionellen regelbasierten Systemen oder anderen maschinellen Lerntechniken in Betracht, um dessen Stärken und Schwächen hervorzuheben.
    
- **Software und Werkzeuge**: Verwenden Sie Python, PyTorch oder TensorFlow zur Implementierung von RL-Algorithmen sowie die CARLA-Python-API zur Integration Ihrer Modelle mit dem Simulator.
    

Indem Sie sich auf diese Bereiche konzentrieren, können Sie eine umfassende und aufschlussreiche Arbeit erstellen, die die Anwendung von Reinforcement Learning im autonomen Fahren mit dem CARLA-Simulator erforscht. Lassen Sie mich wissen, ob Sie weitere Unterstützung oder spezifische Details zu einem bestimmten Abschnitt benötigen!


!!!!!!!!!!!!!!!!!!

The biggest advantage of reinforcement learning (RL) is its ability to learn optimal decision-making policies through interaction with an environment, without requiring explicit instructions on what actions to take. This ability to learn from experience and improve over time makes RL particularly powerful for complex and dynamic problems where the best actions are not immediately obvious or known.

### Key Advantages of Reinforcement Learning

1. **Learning from Interaction**:
    
    - RL learns directly from interactions with the environment, which allows it to adapt and improve its behavior based on feedback. This is especially useful in environments where the system needs to learn from trial and error, such as in games, robotics, and autonomous driving.
2. **Handling Complex Problems**:
    
    - RL excels in situations where the environment is complex and the decision space is large. It can manage multi-step decision-making processes and optimize for long-term goals, making it ideal for applications like playing strategic games or navigating through dynamic environments.
3. **Adaptability and Generalization**:
    
    - RL agents can generalize their learning to new, unseen situations. This adaptability is crucial in environments that are non-stationary or have a high degree of variability, as it allows the agent to modify its strategies in response to changes.
4. **Exploration vs. Exploitation**:
    
    - RL inherently balances exploration (trying new actions to discover their effects) and exploitation (choosing known actions that yield high rewards). This balance enables RL agents to find optimal strategies that might not be apparent at first glance.
5. **Minimal Need for Pre-Defined Models**:
    
    - Unlike supervised learning, which requires labeled data, RL does not need explicit examples of the correct actions. This reduces the need for extensive labeled datasets and allows the agent to learn directly from the consequences of its actions.
6. **End-to-End Learning**:
    
    - RL can learn end-to-end policies, mapping raw inputs (like images or sensor data) directly to actions. This capability simplifies the development pipeline, as it reduces the need for hand-crafted features or intermediate representations.
7. **Versatility**:
    
    - RL is versatile and can be applied to a wide range of problems, from simple tasks like cart-pole balancing to more complex domains like autonomous vehicle control and robotic manipulation.

### Applications and Implications

- **Robotics**: RL enables robots to learn complex manipulation tasks, adapt to new environments, and improve their performance over time through continuous learning.
    
- **Autonomous Vehicles**: In autonomous driving, RL helps develop policies for navigation, obstacle avoidance, and decision-making in dynamic traffic environments.
    
- **Game Playing**: RL has achieved superhuman performance in games like Go, Chess, and StarCraft II by learning strategies that optimize long-term rewards.
    
- **Finance and Trading**: RL is used to develop trading strategies that adapt to market changes and maximize returns.
    
- **Healthcare**: In personalized medicine, RL can optimize treatment strategies based on patient-specific data, leading to better outcomes.
    

In summary, the ability of reinforcement learning to autonomously discover and optimize strategies through interaction and experience makes it a powerful tool for tackling complex, dynamic problems where predefined rules or labeled examples are not feasible. This flexibility and adaptability are key reasons for its success across various domains.


Carla:
Fahrzeuge, typen, 
Maps, custom maps, waypoints, ... (a*, oder einfach über waypoints)
Sensoren, attribute, Sensorfusion?
