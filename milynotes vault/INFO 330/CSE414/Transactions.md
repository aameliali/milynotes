---
order: 29
---

## Concurrency Anomalies

Dirty/Inconsistent Read
- happens when data is read "during" a write
	• Write-Read (WR) conflict

Unrepeatable Read
- happens when data is read prior to a change
	-  Read-Write (RW) conflict

Phantom Read
- happens when data is read prior to an addition/deletion
	• Read-Write (RW) conflict

lost update
- when a write "disappears"
	- A Write-write (WW) conflict


## Transactions & ACID

#### ACID

- Atomic
	- An operation is atomic if everything works or nothing happens
- Consistent
	- Integrity constraints and application specification
- Isolated
	- Isolated behavior is as if an operation ran as if it was the only one running
	- The most important feature of ACID
- Durable
	- Crash recovery
		- What if the database fails in the middle of our atomic transaction?


## Schedules & Serializability

Transactions are sequence of element reads and/or writes
• $R_i(A) \space \rightarrow$ read element A
• $W_i(A) \space \rightarrow$ update element A

Schedules are a sequence of interleaved actions from all transactions

#### Serial Schedules

A **serial schedule** is a schedule where each transaction is executed in some order, one after the other

A **serializable schedule** is a schedule where transactions are executed with possible interleaving, but it appears to the outside as if they were executed in serial order


## Conflict Serializability

We define operation “conflicts” and check for their interactions in a schedule

Most application concurrency problems are describable by conflicts
- Lost Update $\rightarrow$ Write-Write (WW) conflict
- Dirty Read $\rightarrow$ Write-Read (WR) conflict
- Unrepeatable Read $\rightarrow$ Read-Write (RW) conflict
- Phantom Read

Types of Conflicts
- Intra-transaction conflicts
	- Operations within a transaction cannot be swapped
- Inter-transaction conflicts
	- WW conflicts $\rightarrow$ $W_1(X)$, $W_2(X)$
	- WR conflicts $\rightarrow$ $W_1(X)$, $R_2(X)$
	- RW conflicts $\rightarrow$ $R_1(X)$, $W_2(X)$


A schedule is **conflict serializable** if it can be transformed into a serial schedule by a series of swappings of adjacent non-conflicting actions

![[file-20261102111700596.png|598]]




## Precedence Graphs

## Locks & 2PL

## Strict 2PL & Recoverability

## Isolation Levels
