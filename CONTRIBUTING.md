# Contributing

Contributions are welcome. This project is intended to become a reusable, openly licensed course for computational researchers, so improvements to both the technical material and the teaching experience are valuable.

## Ways to contribute

Useful contributions include:

- corrections to technical explanations;
- clearer examples or diagrams;
- new scientific workloads and exercises;
- benchmark improvements;
- accessibility and teaching improvements;
- fixes to code, notebooks, or environment setup;
- feedback from instructors or students who have used the material.

For substantial changes, please open an issue first so the intended learning outcome and scope can be discussed before implementation.

## Development workflow

1. Create a focused branch from `main`.
2. Make small, reviewable commits.
3. Add or update tests when changing executable material.
4. Keep examples reproducible and avoid committing generated datasets or large binary artifacts unless they are essential teaching fixtures.
5. Open a pull request explaining both the technical change and, where relevant, the teaching motivation.

## Conventional Commits

This repository uses the [Conventional Commits](https://www.conventionalcommits.org/) specification.

Commit messages should have the form:

```text
<type>[optional scope]: <description>
```

Common types are:

- `feat:` new course functionality, exercises, or executable material;
- `fix:` corrections to code or behaviour;
- `docs:` course notes, explanations, README changes, or other documentation;
- `test:` tests and validation material;
- `refactor:` structural changes that do not alter behaviour;
- `perf:` performance-focused changes or benchmark improvements;
- `chore:` repository maintenance, tooling, licences, and housekeeping;
- `ci:` continuous-integration changes.

Examples:

```text
docs: explain parquet predicate pushdown
feat(wav): add raw PCM encoding exercise
perf(query): benchmark column projection
fix(storage): preserve float32 dtype when reading binary data
```

Use the imperative mood and keep the first line concise. Add a body when the motivation or trade-off is not obvious from the diff.

Breaking changes should use `!` or a `BREAKING CHANGE:` footer as defined by the specification.

## Teaching material

Examples should support the central course principle: introduce systems ideas through concrete computational problems rather than as isolated abstractions.

Where possible, an exercise should make the cost or limitation of a naive approach observable before introducing the technique that improves it.

Benchmarks should be reproducible and should report enough context to make comparisons meaningful. Prefer explaining *why* a result changes over presenting timings without a systems model.

## Licensing contributions

By contributing, you agree that:

- source code and software examples you contribute are made available under the MIT License;
- teaching material and documentation you contribute are made available under CC BY 4.0;
- you have the right to submit the contribution under those terms.

See [`LICENSE`](LICENSE) and [`LICENSE-CONTENT.md`](LICENSE-CONTENT.md).
