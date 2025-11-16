# **🏇** 

# **README — Japanese Horse Racing Database (Obsidian-based)**

```
# Japanese Horse Racing Knowledge Base (Obsidian + Dataview)

This repository is an experiment in treating **Obsidian** as a lightweight, NoSQL-style **document database** for Japanese horse racing analysis.

Instead of spreadsheets or SQL tables, every **race**, **jockey**, and **entity** exists as a Markdown document with structured metadata (YAML frontmatter).  
Relationships are handled by **Wiki links**, enabling Dataview queries similar to JOIN operations.

This approach focuses on:

- **Flexible schema** (easy to evolve over time)
- **Data reusability** (e.g., jockey → referenced across many races)
- **Queryable structure** (Dataview = analysis engine inside the notes)
- **Future portability** (data can later be exported to SQL/Python for ML)

---

## 🧱 Project Structure
```

/races       # one file = one race

/jockeys     # dimension table for jockey information

README.md

````
Example frontmatter from a race file:

```yaml
date: 2025-11-15
course: Tokyo
surface: Turf
track_condition: Soft
distance: 2000
finish_pos: 4
win_odds: 4.1
jockey: "[[jockeys/C. Lemaire]]"
````

This allows the system to **filter, group, and aggregate** by any field.

---

## **🔍 Dataview Example (Jockey Performance Table)**

```
TABLE date, course, surface, distance, finish_pos, win_odds
FROM "races"
WHERE jockey = this.file.link
SORT date DESC
```

This query placed inside a jockey file returns all races linked to that jockey —

creating a living **performance dashboard** inside the notes themselves.

---

## **🎯 Goals**

- Build a scalable **knowledge graph** for Japanese racing
    
- Analyze jockey tendencies, track biases, and ROI
    
- Provide a public, transparent data structure others can extend
    
- Bridge the gap between **note-taking** and **real analytics**
    

  

Eventually, the dataset can be integrated with:

- **Python** (Pandas for modeling & ML)
    
- **SQL** (for large-scale stats)
    
- **Visualization tools**
    

---

## **🤝 Contribution**

  

This is a work-in-progress project.

Pull requests and issue discussions are welcome — especially regarding:

- Better schema design
    
- Internationalization
    
- Data automation & imports
    
- Additional racing entities (horses, trainers, etc.)
    

---

## **License**

  MIT License — use freely, build boldly.
