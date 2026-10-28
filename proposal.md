# Community Software Analysis Proposal
Please edit this file and push to your repository.

## Software: QuantLib
(https://github.com/lballabio/quantlib)

*Write a paragraph describing what the software does and who its
primary audience is.*

QuantLib is a free, OS C++ library (with Python bindings too, not sure which ill use, probably python) for quantitative finance. More specifically pricing and risk managing derivatives such as options, bonds, swaps, and credit default swaps. Under the hood it is a big collection of numerical methods weve learned like 1D root-finders for backing out implied volatilities and bootstrapping yield curves, interpolation schemes for building term structures, finite difference PDE solvers, Monte Carlo and quasi Monte Carlo engines, numerical integration, and optimizers for model calibration. Its  audience is quantitative analysts, risk managers, and developers at banks, hedge funds, trading firms, and fintech vendors, along with academics and students in financial engineering who use it as a reference implementation.

### Stats

| Description | Your answer |
|---------|-----------|
| Repository URL |  https://github.com/lballabio/QuantLib , https://github.com/lballabio/QuantLib-SWIG  |
| Main/documentation website | https://www.quantlib.org   |
| Year project was started | 2000  |
| Number of contributors in the past year | 103  |
| Number of contributors in the lifetime of the project | ~371  |
| Number of distinct affiliations | >10 |
| Where do development discussions take place? |  GitHub issues, pull request,   (https://www.quantlib.org/mailinglists.shtml)  |
| Typical number of emails/comments per week? | ~80 comments / week  |
| Typical number of commits per week? | ~29, 1520 commits since last year  |
| Typical commit size | `git log --shortstat` median is 2 files with about 24 line changed, mean is larger at about 2400 lines changed |
| How does the project accept contributions? | pull request -> reviewed and merged  |
| Does the project have an automated test suite? | yes |
| Does the project use continuous integration? | yes |
| Does the project have an AI contribution policy? | couldnt find a formal policy but it does have a AI agent guide via https://github.com/lballabio/QuantLib/blob/master/AGENTS.md |
| Are any legal/licensing steps required to contribute? | no  |

### Install and run

Check the following boxes when complete or add a note below if you
encountered a problem.

- [X] I have installed the software
- [X] I have run at least one example
- [X] (Veiw Notes)] I have run the test suite
- [X] The test suite passes

### Notes/concerns/risks

Please comment on any anomalies or known risks to following this
project, if you were unable to answer any questions above, or
otherwise have concerns about the appropriateness of the software.  If
the project requires a contributor license agreement or other
procedural steps, please explain here.  "None at this time" is
acceptable for this question.

6 test / 224 test failed
Switch by using the latest official release, 2 harmless test cases still fail :
Both failures are in test_swaption.py (swaption annuity tests). The two annuity calculations differ by ~5e-5 against a 1e-10 tolerance. The test sets the evaluation date to Date.todaysDate(), so its result depends on the day it’s run. The maintainers removed this file upstream on 2026-10-26 (commit 959dbfa) as obsolete and already covered by the C++ test suite.

No concerns, the core library is C++ and builds with CMake/Autotools/Visual Studio, which can be slow to compile; I plan to use the prebuilt Python package

#### Note on copyright
Students retain copyright on any work done in completion of a CU
course, so you are authorized to sign a [contributor license
agreement (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement),
affirm a [developer's certificate of
origin (DCO)](https://en.wikipedia.org/wiki/Developer_Certificate_of_Origin),
etc.  If you have concerns about this, please note them and/or reach
out to Jed directly.
