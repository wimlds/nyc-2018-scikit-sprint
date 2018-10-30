# Crash Course in Contributing to Scikit-learn:  Workflow


### Set up work environment:  virtual environment
```bash
conda create -n sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel
```
### Activate virtual environment:  
```bash
source activate sklearndev
```

## PART A:  Set-up

1.  Pick an issue to work on:  https://github.com/scikit-learn/scikit-learn/issues
2.  Comment on issue with:  *I'm working on this*
3.  Fork repo:  https://github.com/scikit-learn/scikit-learn
4.  Set up local repo  

Note:  for `git clone`, add your forked repo url.  
```bash
git clone https://github.com/reshamas/scikit-learn.git
git remote add upstream https://github.com/scikit-learn/scikit-learn.git
```
Check remotes are there using `git remote -v`
```bash
origin	https://github.com/reshamas/scikit-learn.git (fetch)
origin	https://github.com/reshamas/scikit-learn.git (push)
upstream	https://github.com/scikit-learn/scikit-learn.git (fetch)
upstream	https://github.com/scikit-learn/scikit-learn.git (push)
```
5.  Update local repo
```bash
git pull upstream master
```
6. Fetch someone else's PR:
```bash
git fetch https://github.com/theirusername/reponame.git theirbranch:ourbranch
```

## PART B:  Fixing issue
- Explore and fix issue.  This will take the majority of time (!)


## PART C:  Committing change 

- Make updates to file
- Create feature branch

```bash
git checkout -b <feature_branch>
```

- Commit changes to branch

```bash
git add <file_name>
git commit -m 'description for fix'
```


## PART D:  Run tests

#### `flake8` formatting test
- `flake8` tests for formatting errors

```bash
flake8 <file_name>
```

#### `pytest sklearn` tests
- Run tests  
```bash
pytest sklearn
```

#### Run tests on individual test files  
- Create test file  
- Run test file

```bash
pytest <test_file>
```

>example
```bash
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/check_estimator_regression-test_draft.py
```

## PART E:  Submit Pull Request (PR)
#### After all tests have passed, push update file(s) to feature branch
```bash
git push origin <feature_branch>
```

#### Submit PR  
Do this on GitHub


## Part F:  Regression Tests on GitHub
These tests happen automatically after a PR has been submitted.

<img src="images/reg_tests.png"  />
 
---

## Formatting Tests
What is [flake8](https://medium.com/python-pandemonium/what-is-flake8-and-why-we-should-use-it-b89bd78073f2)?

Can install using `pip` or `conda`:  
Example:  
```python
conda install flake8 
```

### Running `flake8`
`flake8` <filename.py>
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



