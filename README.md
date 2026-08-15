# Systems for Scientific Computing

**Systems for Scientific Computing** is a practical course on the systems foundations of scientific software: how data is represented, stored, accessed, queried, and moved through computational workflows.

The course is intended for computational researchers and scientific programmers who already know how to write code, but want a stronger mental model of what happens beneath high-level scientific Python and dataframe APIs.

## Purpose

Modern scientific work routinely involves large arrays, simulation outputs, tabular data, meshes, trajectories, experimental measurements, and generated data from computational algorithms. Researchers need to read, write, search, filter, aggregate, join, serialize, and move these data efficiently and reliably.

This course develops the systems literacy needed to reason about those operations.

Its central principle is that the performance and scalability of scientific software depend not only on the mathematical algorithm, but also on how data is physically represented and accessed.

The course therefore connects high-level scientific workflows to the layers beneath them:

```text
scientific problem
      ↓
data access pattern
      ↓
algorithm and data structure
      ↓
memory representation
      ↓
storage layout
      ↓
disk and network traffic
```

## Learning objectives

By the end of the course, students should be able to:

- reason about numerical data as typed bytes in memory and on disk;
- understand how dtypes, array layout, strides, views, copies, and memory mapping affect computation;
- explain the trade-offs between text, binary, row-oriented, column-oriented, and chunked storage formats;
- choose storage formats and layouts according to expected access patterns;
- interpret common dataframe operations such as filtering, grouping, sorting, and joining in algorithmic terms;
- understand how indexing, hashing, sorting, and partitioning arise from concrete data-access requirements;
- reason about out-of-core workflows when data exceeds available memory;
- understand the role of locality, serialization, partitioning, and network movement in distributed scientific computation;
- identify when performance can be improved by reducing unnecessary data movement rather than accelerating arithmetic.

## Course content

The material is organized around four complementary themes.

### Representation

How numerical data is represented in memory and on disk.

Topics include binary representation, typed values, endianness, serialization, NumPy dtypes, contiguous arrays, strides, memory layout, direct binary I/O, and memory mapping.

### Storage

How file formats and physical layout affect the cost of scientific data access.

Topics include CSV, raw binary data, NumPy formats, Parquet, HDF5, Zarr, columnar storage, chunking, compression, projection, predicate pushdown, and partial reads.

### Querying

How common dataframe operations map to algorithms and data structures.

Topics include scans, filtering, aggregation, grouping, sorting, repeated lookup, indexes, joins, hashing, and range queries. Pandas is used as a familiar interface through which these underlying operations can be examined.

### Distribution

How data-intensive scientific workflows change when computation spans processes or machines.

Topics include partitioning, data locality, serialization, network transfer, distributed aggregation, joins, shuffles, and the relationship between computational work and data placement.

## Practical approach

The course is exercise-driven. Students work with concrete scientific and numerical data problems and inspect the consequences of different representations, storage layouts, and algorithms.

Exercises are designed to connect low-level mechanisms to high-level scientific workflows. Examples include constructing binary data formats directly, comparing storage formats under different query patterns, implementing simplified versions of dataframe operations, and working with partitioned simulation or generated scientific data.

The emphasis is on transferable mental models rather than mastery of any one library or technology.

## Delivery

The material is modular. It can be delivered as a single standalone session, a workshop, or a sequence of sessions with progressively deeper treatment of representation, storage, querying, and distributed execution.

Python, NumPy, and pandas are used for many examples because of their ubiquity in scientific computing, but the systems principles are language-independent.

## Repository

This repository contains the course materials and supporting software, including exercises, executable demonstrations, benchmark experiments, teaching notes, and reference material.

The project is under active development.

## Contributing

Contributions, corrections, examples, and teaching feedback are welcome. See [`CONTRIBUTING.md`](CONTRIBUTING.md) for contribution guidelines.

This repository uses [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

## Licensing

The project is intended to be openly reusable.

- **Code and software examples** are licensed under the MIT License.
- **Teaching material and documentation** are licensed under Creative Commons Attribution 4.0 International (CC BY 4.0).

See the repository licence files for details.
