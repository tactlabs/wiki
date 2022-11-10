/ [Home](index.md)

# RASA BASIC SETUP

### Installation:

1. create a new conda environment 
```
conda create -n rasa -y python=3.8
```
2. install rasa
```
pip install rasa
```
3. incase of pip error, upgrade pip
```
python -m pip install --upgrade pip
```
4. create a directory
```
mkdir rasa-test
```
5. create an initial model
```
rasa init
```

### To run in terminal:
```
rasa shell
```

### To create a new intent:

1. add new intent in nlu.yml file:
```
- intent: food 
  examples: |
    - give me a food recommendation.
    - recommend food
```
2. add a response in domain.yml file:
```
  utter_food:
  - text: "Noodles"
```
3. create a rule for the intent in rules.yml
```
- rule: Say "noodles" when food
  steps:
  - intent: food
  - action: utter_food
```
4. train the model (run in terminal)
```
rasa train
```
5. run the bot 
```
rasa shell
```