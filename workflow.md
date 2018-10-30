

## Formatting Tests
What is [flake8](https://medium.com/python-pandemonium/what-is-flake8-and-why-we-should-use-it-b89bd78073f2)?

Can install using `pip` or `conda`:  
Example:  
```python
conda install flake8 
```

### Running `flake8`
`flake8` filename.py
```bash
flake8 /Users/reshamashaikh/scikit-learn/sklearn/metrics/scorer.py
```

When there are formatting issues, here's an example of what it will return:
```bash
(sklearndev) % flake8 scorer.py
scorer.py:186:39: E225 missing whitespace around operator
scorer.py:189:80: E501 line too long (85 > 79 characters)
scorer.py:190:80: E501 line too long (87 > 79 characters)
```

# Workflow for Open Source

## PART A:  Set-up

1.  Pick an issue to work on
2.  Comment on issue with "I'm working on this"
3.  Set up local repo ready:  
Note:  for `git clone`, add your forked repo url.  
```python
git clone https://github.com/reshamas/scikit-learn.git
git remote add upstream https://github.com/scikit-learn/scikit-learn.git
```


## PART B:  Fixing Issue

1.  Explore and fix issue.  This will take the majority of time (!)


## PART C:  Committing Change, running tests, submitting PR

1.  Make updates to file
2.  Create feature branch
3.  Commit changes to branch
4.  Run formatting tests (using flake8)
5.  Run other tests?   (GMM, regression)
6.  After all tests have passed, push update file(s) to feature branch
7.  Submit PR


