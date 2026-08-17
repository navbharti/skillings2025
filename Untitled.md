
## [Advitiya](https://www.codechef.com/problems/ADVITIYA1)

**IIT Ropar** is hosting its annual tech fest, **Advitiya**, on the **16th, 17th, and 18th of February**.

Mehul, looking for a vacation, decides to visit Ropar in the month of February. He learned of Advitiya and found out that there are no registration fees — even accommodation is being provided to the participants for free! Team Advitiya is very welcoming, so Mehul definitely wants to attend the fest.

Mehul will visit Ropar on date $N$ (where $1 \le N \le 18$) of February. Will he be able to enjoy the fest?

### Input Format

* The first line contains a single integer $N$, the date on which Mehul decided to visit Ropar.

### Output Format

* Print a single line containing the answer:
* `ADVITIYA` if Mehul visits during the fest dates.
* `WAITING FOR ADVITIYA` otherwise.


* *Note: The output is case-insensitive (e.g., `advitiya` and `ADVITIYA` are both accepted).*

### Constraints

* $1 \le N \le 18$

---

### Sample Cases

| Input | Output |
| --- | --- |
| `5` | `WAITING FOR ADVITIYA` |
| `17` | `ADVITIYA` |

#### Explanation

* **Sample 1:** Advitiya starts on the 16th, but Mehul is visiting on the 5th, which is too early.
* **Sample 2:** Advitiya runs from the 16th to the 18th, so Mehul visits right in the middle of the fest!

---

### Quick Implementation Tip (Python)

Since the dates are continuous (16, 17, 18), you can solve this using a simple comparison:

```python
N = int(input())
if 16 <= N <= 18:
    print("ADVITIYA")
else:
    print("WAITING FOR ADVITIYA")

```

