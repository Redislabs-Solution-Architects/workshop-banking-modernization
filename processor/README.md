# Processor Modules

## The Scenario

You're building the backend for a banking app. Transactions are streaming in every few seconds. 

Your job is to store them using Redis's native data structures so each query is instant:
- No filtering through raw data
- No sorting at query time
- Data is stored ready to serve

The [`consumer.py`](consumer.py) already reads from the Redis Stream and calls your modules. You just complete the TODOs.

---

## Module 1: Ordered Transactions (Redis List)

**Goal:** *"Show me my last 20 transactions"*

Store transaction IDs in order so we can fetch the most recent ones instantly.

**File:** [`modules/ordered_transactions.py`](modules/ordered_transactions.py)

> Stuck? See [`solutions/ordered_transactions.py`](solutions/ordered_transactions.py)

⚠️ **Complete Module 2 before restarting** — the Transactions tab needs both modules to work.

---

## Module 2: Store Transaction (Redis JSON)

**Goal:** *"Show me the details of this transaction"*

Store the full transaction object so we can display all the details when clicked.

**File:** [`modules/store_transaction.py`](modules/store_transaction.py)

> Stuck? See [`solutions/store_transaction.py`](solutions/store_transaction.py)

✅ **Now restart to see the Transactions tab:**
```bash
docker compose restart processor
```

---

## Module 3: Spending Categories (Sorted Set)

**Goal:** *"Where am I spending the most?"*

Track running totals by category and merchant — Redis keeps them sorted automatically.

**File:** [`modules/spending_categories.py`](modules/spending_categories.py)

> Stuck? See [`solutions/spending_categories.py`](solutions/spending_categories.py)

✅ **Restart to see the Categories tab:**
```bash
docker compose restart processor
```

---

## Module 4: Spending Over Time (TimeSeries)

**Goal:** *"How has my spending changed this week?"*

Store timestamped spending data for time-range queries.

**File:** [`modules/spending_over_time.py`](modules/spending_over_time.py)

> Stuck? See [`solutions/spending_over_time.py`](solutions/spending_over_time.py)

✅ **Restart to see the Spending Chart:**
```bash
docker compose restart processor
```

---