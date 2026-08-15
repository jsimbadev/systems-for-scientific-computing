# Systems for Scientific Computing

A practical course on the systems foundations that make scientific data workflows understandable, efficient, and scalable.

The course starts from familiar scientific Python and dataframe workflows, then progressively exposes the layers underneath them: numerical representation, raw bytes, memory layout, file formats, query execution, data structures, storage layout, and distributed computation.

The central question throughout is:

> **What work is the machine actually doing, and which bytes really need to move?**

## Why this course?

Scientific programmers routinely search, filter, aggregate, join, serialize, store, and move data. High-level tools make these operations convenient, but convenience can hide the physical work being performed.

This course is designed to build a systems-level mental model for computational research. Rather than teaching data structures, databases, or distributed systems in isolation, it introduces them when a scientific workload makes them necessary.

A recurring progression is:

```text
scientific question
        ↓
high-level operation
        ↓
algorithm
        ↓
data structure
        ↓
memory / storage representation
        ↓
disk / network traffic
```

The goal is not to turn scientists into database engineers. It is to make scientific programmers able to reason about performance, representation, storage, and scale instead of treating these layers as black boxes.

## Course structure

The material is being designed to work at multiple resolutions: a single standalone session, a half-day workshop, or a multi-session mini-course.

### 1. Representation — data is bytes

**Focus:** what numerical data physically is.

Topics include:

- binary representation and typed values;
- `struct`, offsets, endianness, and serialization;
- NumPy dtypes and contiguous arrays;
- strides, views, copies, and memory layout;
- memory mapping and partial access.

A planned opening exercise constructs a valid WAV file directly from raw bytes: generate a sinusoid, quantize the samples, write the header and payload, and play the resulting file. The point is not audio programming; it is to make schema, layout, types, offsets, and serialization tangible.

### 2. Storage — file formats are data structures

**Focus:** how physical layout determines which access patterns are cheap.

Topics include:

- text versus binary formats;
- CSV, NumPy formats, Parquet, HDF5, and Zarr;
- row-oriented and column-oriented layouts;
- chunking and compression;
- projection and predicate pushdown;
- reading fewer bytes rather than processing unnecessary data faster.

### 3. Querying — what is a dataframe operation really doing?

**Focus:** interpreting familiar pandas workflows as computational operations.

Examples include:

- filtering as scanning and predicate evaluation;
- `groupby` as aggregation;
- `merge` as a join;
- sorting and indexing;
- repeated lookup and range queries.

This section motivates data structures and algorithms from concrete workloads rather than treating them as interview exercises.

### 4. Distribution — data lives somewhere

**Focus:** what changes when data no longer fits comfortably in one process or on one machine.

Topics include:

- partitioning and data locality;
- serialization and network movement;
- shuffles and distributed joins;
- local aggregation;
- moving computation to data versus moving data to computation;
- scientific workloads built from generated simulation or inference data.

## Teaching philosophy

The course follows one rule wherever possible:

> **Do not introduce a systems abstraction before the workload gives students a reason to want it.**

A slow repeated scan motivates an index. A huge CSV motivates columnar storage. A dataset larger than memory motivates streaming and memory mapping. A distributed join motivates partitioning and shuffles.

The intended pattern is:

```text
experience the problem
        ↓
explain the physical work
        ↓
introduce the engineering response
```

## Audience

The course is intended primarily for computational researchers and scientific programmers who already have some programming experience but want a stronger mental model for the systems beneath their workflows.

Examples are expected to use Python, NumPy, and pandas because of their ubiquity in scientific work, but the underlying ideas are language-independent.

## Status

This repository is in early development. The first goal is to produce and deliver the course, gather feedback, and iterate on the exercises before publishing a polished public release.

Planned material will include:

- lecture notes;
- executable demonstrations;
- hands-on exercises;
- benchmark experiments;
- instructor notes;
- reference solutions where appropriate;
- a scientific capstone connecting storage, queries, and distributed execution.

## Contributing

Contributions, corrections, examples, and teaching feedback are welcome. See [`CONTRIBUTING.md`](CONTRIBUTING.md) once the initial project scaffold is merged.

This repository uses [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

## Licensing

This project is intended to be openly reusable.

- **Code** is licensed under the MIT License.
- **Teaching material and documentation** are licensed under Creative Commons Attribution 4.0 International (CC BY 4.0).

See the licence files in the repository for details.
