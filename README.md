# Workflow

Specify file sequence starting from _base_ file. Merge starts from base and merges each next file in sequence in same order as specified.
```bash
arm-combine -f base.json -f first.json -f second.json
```

# Rules for merging

## Dictionary

|   A      |   B   | result |
| ---------|-------|--------|
| key1::smiling_imp:<br>key2::alien: | | key1::smiling_imp:<br>key2::alien: |
| key1::smiling_imp: | key2::sunglasses: | key1::smiling_imp:<br>key2::sunglasses: |
| key1::smiling_imp:<br>key2::alien: | key2::sunglasses:<br>key3::neckbeard: | key1::smiling_imp:<br>key2::sunglasses:<br>key3::neckbeard: |

## Array

|   A      |   B   | result |
| ---------|-------|--------|
| \- ele1<br>\- ele2 | | \- ele1<br>\- ele2 |
| \- ele1 | \- ele2 | \- ele1<br>\- ele2 |
| \- ele1<br>\- ele2 | \- ele3 | \- ele1<br>\- ele2<br>\- ele3 |
