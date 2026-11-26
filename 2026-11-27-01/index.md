---
title: "The Feynman technique for CS students"
---

# The Feynman technique for CS students

A study method named after physicist Richard Feynman: if you can't explain a concept in plain words, you've found the exact spot where your understanding breaks. It works for DSA, OS, DBMS and CN, and it doubles as interview practice, because interviews make you explain your approach out loud.

Where the idea comes from: a June 2017 kottke.org post retells a story from Feynman's colleague David Goodstein. Feynman offered to prepare a freshman lecture on a hard physics question, then came back and said: "I couldn't do it. I couldn't reduce it to the freshman level. That means we don't really understand it."

## The 4 steps
1. **Pick one concept.** Small and specific: "deadlock", not "operating systems".
2. **Explain it to a 12-year-old.** On paper or out loud. No jargon, no copying the textbook definition.
3. **Find the gaps.** Every place you stalled, hand-waved or reached for jargon is a gap. Go back to the source for just that part.
4. **Simplify + add an analogy.** Rewrite it shorter. Add one everyday analogy and one tiny example.

## 1-page template (copy this)
```
Concept: ____________   Date: ______
1. Plain-words explanation (5 lines max):
2. One analogy:
3. One tiny example (input -> output, or a 3-line trace):
4. Where I got stuck (the gaps):
5. Source I re-read for each gap:
6. Final version, 3 sentences:
7. One interview question this answers:
```

## 10 CS concepts to practise on
1. Recursion (and the base case)
2. Hash map (and collisions)
3. Binary search
4. Dynamic programming vs plain recursion
5. Process vs thread
6. Deadlock (and its 4 conditions)
7. Virtual memory and paging
8. Database index
9. ACID transactions
10. TCP vs UDP

Do one a day. Say your final version out loud in under 2 minutes, like you would in an interview.

## Free resources to fill the gaps
- **CS50x 2026** (https://cs50.harvard.edu/x/): Harvard's intro to CS, free through OpenCourseWare. Weeks cover C, arrays, algorithms, memory, data structures, Python, SQL, web and Flask. Good for recursion, hash tables and memory.
- **Operating Systems: Three Easy Pieces (OSTEP)** (https://pages.cs.wisc.edu/~remzi/OSTEP/): by Remzi and Andrea Arpaci-Dusseau. Every chapter is a free PDF (the authors say it "is and will always be free"). Use the Virtualization and Concurrency chapters for processes, paging, locks and deadlock.
- **Use The Index, Luke** (https://use-the-index-luke.com/): the free web edition of Markus Winand's book *SQL Performance Explained*. Explains SQL indexing for developers, with notes for MySQL, PostgreSQL, Oracle, SQL Server and Db2.

## Sources (checked 26 Nov 2026)
- https://kottke.org/17/06/if-you-cant-explain-something-in-simple-terms-you-dont-understand-it
- https://cs50.harvard.edu/x/
- https://pages.cs.wisc.edu/~remzi/OSTEP/
- https://use-the-index-luke.com/

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
