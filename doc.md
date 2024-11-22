# Transaction

*Ref: Database Systems Concept, by Korth*

## What is a transaction?
A transaction is a unit of program execution that accesses and possibly updates various data items. Usually, a transaction is initiated by a user program written in a high-level data-manipulation language (typically SQL), or programming language (e.g., C++ or Java), with embedded database accesses in JDBC or ODBC.

## ACID
- Atomicity
- Concurrency
- Isolation
- Durability

Atomicity and Durability of a DBMS is managed by **Recovery System**.

Concurrency vs Serialization: Concurrency provides the performance benifits while serialization ensures isolation. The isolation is managed by **concurrency-control system**.

## Storage Structures

- Volatile Storage: does not survive crashes, e.g. Main memory, Cache memory
- Non-volatile Storage: does survive crashes, e.g. Secondary memory like Magnetic disks, flash drives, or tertiary devices like magnetic tapes, etc
- Stable Storage: Information stored here is never lost(never != impossible), e.g. Non-volatile Storage with several stable storage implementation.

Some terms about transactions:
- **Aborted**: A transaction which doesn't complete it's executation successfully is known as aborted
- **Rolled Back**: Once the changes caused by an aborted transaction have been undone, we say that the transaction has been rolled back
- **Committed**: A transaction that completes its execution successfully is said to be committed.
- **Compensating Transaction**: Once a transaction has committed, we cannot undo its effects by aborting it. The only way to undo the effects of a committed transaction is to execute a compensating transaction.

## States of a transaction
- **Active**: the initial state; the transaction stays in this state while it is executing.
- **Partially committed**: after the final statement has been executed.
- **Failed**: after the discovery that normal execution can no longer proceed.
- **Aborted**: after the transaction has been rolled back and the database has been restored to its state prior to the start of the transaction.
- **Committed**: after successful completion.

A transaction is said to have **terminated** if it has either committed or aborted.