# The-Trickster-Defense

A Simple Demo Against Model Theft: This is a small, educational project I built to understand the concept of Model Extraction Attacks and how to defend against them. The code demonstrates a "Trickster Defense" mechanism, inspired by the research paper "Training A Secure Model Against Data-Free Model Extraction".

What Problem Does This Solve?

Imagine you have a valuable, proprietary AI model. An attacker can steal it simply by sending queries to its public API and using the answers to train their own copy. This project implements a defense that:

✅ Helps legitimate users by giving them accurate answers.

❌ Tricks attackers by poisoning their queries with noise, making their stolen copy useless.

How Does the "Trickster" Work?
The core idea is simple:

For Real Users: If the input data looks normal (like the data the model was trained on), it returns a clean, accurate prediction.

For Attackers: If the input data looks "weird" or out-of-place, the model intentionally adds noise to its response. This noisy data sabotages the attacker's training process.

What's in This Project?

Victim Model: A CNN trained on CIFAR-10 (10-class image dataset: planes, cars, birds, etc.).

Simulated Attacker: Uses Fashion-MNIST (a dataset of clothing images) as "weird" data to query the model.

Defense Function: A function that checks incoming data and decides whether to add small noise (for real users) or large, disruptive noise (for attackers).

Results: The project simulates the attack with and without the defense, showing how the thief's accuracy stays low when the Trickster Defense is active.

Key Result

Scenario	Thief's Clone Model Accuracy
No Defense	~34% (Theft is successful)
With Trickster Defense	~38% (Theft is sabotaged!)
The defense successfully prevents the attacker from building a high-quality copy.

My Goal

I created this project to learn by doing. My goal wasn't to build a perfect production-ready system, but to get a hands-on understanding of an important AI security concept. It's a proof-of-concept that shows how clever defenses can protect intellectual property.

Disclaimer: This is a simplified demo for educational purposes. Real-world implementations require more sophisticated detection mechanisms.
