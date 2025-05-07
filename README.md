# Annotated-Munazarat 2.0

Welcome to the Annotated-Munazarat 1.0 corpus! This corpus contains 110 competitive Arabic debates annotated according to a modified Toulmin's annotation scheme.

## Accessing the Corpus

The corpus is organized into two main directories:

* **`data/`**: Contains the annotated debates in CSV format.
  * `training.csv`: The training dataset.
  * `testing.csv`: The testing dataset.
* **`text/`**: Contains the raw, unannotated debate transcripts in `.txt` format, corresponding to the debates in the `data` directory.

You can access the files by cloning this repository or downloading the files directly.

## CSV File Structure

The CSV files (`training.csv` and `testing.csv`) have the following columns:

* `debate_id`: A unique identifier for each debate.
* `start`: The starting character offset of the annotated text segment in the original debate transcript.
* `end`: The ending character offset of the annotated text segment.
* `text`: The actual text segment that has been annotated.
* `label`: The annotation label assigned to the text segment (see explanation below).
* `gender`: The gender of the speaker ('M' for male, 'F' for female).

## Annotation Labels Explained

The `label` column uses the following annotation scheme, categorized by argumentation type, to classify rhetorical and argumentative moves:

### Inferential Argumentation (Logos)

Argumentation based on the logical structure of an argument (Aristotle's Logos), substantiated by Toulmin's categories with additions for the debate corpus.

| Label                  | Explanation                                                                                                                             |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `POSITION`           | Team's position in the debate (proposition or opposition).                                                                              |
| `SUPER CLAIM`        | An assertive statement outlining the team's overall goal.*Note: This label appears in the data but wasn't in the initial list.*       |
| `CLAIM`              | An assertive statement or conclusion the speaker seeks to justify/support or refute/rebut.                                              |
| `GROUND`             | Agreed-upon information, facts, or definitions supporting the claim.                                                                    |
| `WARRANT`            | The logical link connecting `GROUND` to `CLAIM` (often implicit).                                                                   |
| `RATIONAL BACKING`   | Logical/inferential reasoning, justifications, conclusions, or mini-supported assertions supporting the `WARRANT`.                    |
| `EVIDENTIAL BACKING` | Specific examples or research findings provided to support a `CLAIM`, `GROUND`, or `WARRANT`.                                     |
| `QUALIFIER`          | A statement conceding the scope or certainty of a claim.*Note: This label is in your list but wasn't found in the CSV data provided.* |
| `REBUTTAL`           | Refutation or challenge of an opposing team's/individual's claim.                                                                       |

### Expressive Argumentation (Ethos)

Argumentation based on the speaker creating their own credibility, morality, trustworthiness, organization, and order (e.g., authority, honesty, fairness, transparency).

| Label     | Explanation                                                                     |
| --------- | ------------------------------------------------------------------------------- |
| `ETHOS` | Statements appealing to the speaker's credibility, character, or shared values. |

### Appellative Argumentation (Pathos)

Argumentation appealing to the audience's emotions and feelings, attempting to engage them (e.g., empathy, fear, anger, hope, patriotism).

| Label               | Explanation                                                                                                        |
| ------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `PATHOS`          | Statements appealing to the audience's emotions or values.                                                         |
| `SELF-REPETITION` | Partial or total repetition of statements made by the same speaker.                                                |
| `TEAM REPETITION` | Partial or total repetition of statements made by the speaker's team.                                              |
| `RECITATING`      | Partial or total repetition/quoting of statements made by the opposing team, or definitions/laws/common knowledge. |

## Use-Cases

This corpus can be valuable for various Natural Language Processing (NLP) and Argumentation Mining tasks, including:

* **Argument Component Recognition:** Identifying different parts of an argument (Claim, Ground, etc.).
* **Argumentative Zoning:** Classifying sentences or segments based on their argumentative function.
* **Rhetorical Strategy Analysis:** Studying the use of Ethos and Pathos in debates.
* **Argument Generation Models:** Training models to generate argumentative text.
* **Debate Analysis:** Understanding argument structures and strategies in competitive debates.
