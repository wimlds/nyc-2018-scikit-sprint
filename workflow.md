# Crash Course in Contributing to Scikit-learn:  Workflow

---
## PART A:  Set-up work environment

#### Set up virtual environment
```bash
conda create -n sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel
```
#### Activate virtual environment:  
```bash
source activate sklearndev
```

---

## PART B:  Select issue
- Pick an issue to work on:  https://github.com/scikit-learn/scikit-learn/issues
- Comment on issue with:  *I'm working on this*

---

## PART C:  Set-up repository

### Fork repo:  https://github.com/scikit-learn/scikit-learn

### Set up local repo  
#### `git clone` your forked repo url.  

>my example
```bash
git clone https://github.com/reshamas/scikit-learn.git
```

#### Add `upstream` remote
```
git remote add upstream https://github.com/scikit-learn/scikit-learn.git
```

#### Check remotes are there using `git remote -v`

>my example
```bash
origin	https://github.com/reshamas/scikit-learn.git (fetch)
origin	https://github.com/reshamas/scikit-learn.git (push)
upstream	https://github.com/scikit-learn/scikit-learn.git (fetch)
upstream	https://github.com/scikit-learn/scikit-learn.git (push)
```

### Update local repo
```bash
git pull upstream master
```

### Fetch someone else's PR:
```bash
git fetch https://github.com/theirusername/reponame.git theirbranch:ourbranch
```

---

## PART D:  Fixing issue
- Explore and fix issue.  This will take the majority of time (!)
- Make updates to file `<file_name>`

---

## PART E:  Committing change 

#### Create feature branch

```bash
git checkout -b <feature_branch>
```

#### Commit changes to branch

```bash
git add <file_name>
git commit -m 'description for fix'
```

---

## PART F:  Run tests

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

### Create test file

#### Run tests on individual test files  
- Create test file under `tests` directory
- Run test file

```bash
pytest <test_file>
```

>example
```bash
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/test_classifier.py
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/test_mixture.py
```

---

## PART G:  Submit Pull Request (PR)
#### After all tests have passed, push update file(s) to feature branch
```bash
git push origin <feature_branch>
```

#### Submit PR  
Do this on GitHub

---

## Part H:  Regression Tests on GitHub
These tests happen automatically after a PR has been submitted.

<img src="images/reg_tests.png"  />
 
---

## References

### `flake8` Formatting Tests
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



