# Dataset Summary

## Structure
```
project/dataset/raw/{environment}/{element_id}/{action}/
  before.png, after.png, crop.png, delta_mask.png, trajectory.json
project/dataset/processed/trajectories.jsonl
```

## Collection Protocol
1. Discover interactive elements (button, svg, img, menu, tab, toolbar, avatar, input)
2. Max 2 interactions per element: click + hover
3. Wait for GUI stabilization after each action
4. Extract visual diff mask via OpenCV absdiff

## Statistics
- Environments: 5
- Elements: 127
- Trajectories: 200
- Actions: {'click': 127, 'hover': 73}
