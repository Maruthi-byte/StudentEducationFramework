# StudentEducationFramework
# About Me

Hi, I'm Maruthi Varaprasad, an aspiring technology learner and software developer interested in building practical, secure, and user-focused technology.

My learning interests include:

 Software Development
 Linux and Systems
 Cybersecurity
 Artificial Intelligence
 Rust
 Cross-platform Application Development
 Web Technologies
 Education Technology

I enjoy learning difficult technical concepts by breaking them down into structured modules, understanding how the underlying systems work, and then applying that knowledge by building projects.
# 🎓 Education Framework

> An interactive education knowledge graph for exploring **education pathways, courses, eligibility requirements, institution-specific constraints, and future study options**.

## 🌐 Overview

The **Education Framework** represents education as an interactive **knowledge graph**, rather than a conventional tree.

Core concept:

**Student → Qualification → Pathways → Courses → Eligibility → Institutions → Future Pathways**

A student's stream should not permanently restrict the graph. The same course can connect to multiple backgrounds.

Example:

```text
MPC ───────┐
BiPC ──────┤
MEC ───────┤
CEC ───────┼──────► BCA
HEC ───────┘
```

The graph represents the complete education landscape, while the student's profile is used to evaluate eligibility.

---

## 🎯 Goals

- Map the education ecosystem.
- Show multiple pathways after different qualifications.
- Represent shared courses across different streams.
- Explain eligibility using clear text.
- Explain **why** a student is or is not eligible.
- Represent institution-specific admission constraints.
- Support regular, online, and open/distance routes.
- Show future education possibilities after completing a course.
- Support academic-year-specific eligibility rules.
- Provide an interactive, searchable education map.

---

## 🧠 Core Concept

This is a **many-to-many education graph**.

It is not:

```text
MPC → Engineering
BiPC → Medicine
MEC → Commerce
CEC → Commerce
```

Instead:

```text
                    ┌──── B.Tech
                    │
MPC ───────┐        ├──── BCA
BiPC ──────┤        ├──── BBA
MEC ───────┼───────►├──── B.Com
CEC ───────┤        ├──── BA
HEC ───────┘        └──── ...
```

A programme exists as a reusable node and can have multiple incoming and outgoing connections.

---

## 🗺️ Planned Education Structure

```text
STUDENT
   │
   ▼
SCHOOL EDUCATION
   │
   ├── Secondary / 10th
   ├── Intermediate / 10+2
   ├── Polytechnic
   ├── ITI
   ├── Vocational
   └── Other recognised pathways
           │
           ▼
       COURSE NETWORK
           │
   ┌───────┼────────┐
   ▼       ▼        ▼
  UG      Diploma   Other
   │
   ▼
  PG
   │
   ▼
Research / PhD
   │
   ▼
Career / Further Education
```

---

## 📚 Course Categories

The long-term catalogue is intended to cover:

- Engineering & Technology
- Computer Science & IT
- Computer Applications
- Basic Sciences
- Medicine
- Dental
- AYUSH
- Pharmacy
- Nursing
- Allied Health / Paramedical
- Agriculture & Allied Sciences
- Veterinary
- Fisheries
- Forestry
- Commerce
- Management
- Economics
- Humanities
- Social Sciences
- Law
- Architecture
- Planning
- Design
- Fine Arts
- Education
- Journalism & Mass Communication
- Social Work
- Hospitality & Tourism
- Aviation
- Maritime
- Vocational Education
- Diploma / Polytechnic
- Open & Distance Learning
- Online Education
- Other recognised programmes

The catalogue will be expanded progressively.

---

## 🔍 Eligibility Model

Eligibility is **not** stored simply as:

```text
BCA → MPC = Eligible
```

Instead:

```text
STUDENT PROFILE
      +
PROGRAMME
      +
INSTITUTION
      +
ACADEMIC YEAR / SESSION
      +
ELIGIBILITY RULES
      ↓
ELIGIBILITY EVALUATION
```

Possible results:

- **ELIGIBLE**
- **CONDITIONAL**
- **NOT ELIGIBLE**
- **CHECK DETAILS**
- **NOT YET ELIGIBLE**

### Example

One institution may allow:

```text
BCA
Any 10+2 stream
```

while another may require:

```text
BCA
Mathematics / Computer Science required
```

The framework therefore stores both rules instead of declaring that BCA universally requires or does not require Mathematics.

---

## 🏫 Institution-Specific Constraints

Each programme should eventually support institution-level rules.

Example:

```text
BCA
│
├── Institution A
│   ├── Qualification: 10+2
│   ├── Stream: Any
│   ├── Mathematics: Not required
│   └── Minimum marks: Institution-specific
│
├── Institution B
│   ├── Qualification: 10+2
│   ├── Mathematics: Required
│   └── Minimum marks: Institution-specific
│
└── Institution C
    ├── Mathematics OR Computer Science
    └── Entrance examination may apply
```

This allows the framework to explain **why** eligibility differs between institutions.

---

## 🖥️ Interface Concept

The interface is inspired by interactive network/knowledge frameworks rather than a traditional tree.

### Interaction

1. Start with **Student**.
2. Click a node to reveal the next level.
3. Open **Intermediate / 10+2**.
4. Select **MPC, BiPC, MEC, CEC, HEC**, etc.
5. Expand course pathways.
6. Select a course.
7. View detailed information in the side panel.
8. Explore eligibility and institution-specific constraints.
9. Continue into postgraduate and future pathways.

The graph is intended to support:

- Click-to-expand
- Click-to-collapse
- Search
- Zoom
- Pan
- Shared/reusable nodes
- Multiple incoming connections
- Multiple outgoing connections
- Side-panel descriptions

---

## 🧩 Programme Information Model

A programme node can contain:

```text
Programme
├── Name
├── Level
├── Category
├── Description
├── Duration
├── Specialisations
├── Possible entry backgrounds
├── Required subjects
├── Minimum marks
├── Entrance examinations
├── Admission methods
├── Study modes
│   ├── Regular
│   ├── Online
│   └── ODL
├── Institutions
├── Institution-specific constraints
├── Fees
├── Scholarships
├── Required documents
├── Higher-study pathways
├── Career pathways
└── Sources / verification information
```

---

## 🗃️ Planned Data Model

The production system should separate these entities:

```text
STUDENT
   │
   └── PROFILE

PROGRAMME
   │
   ├── CATEGORY
   ├── LEVEL
   └── PROGRESSION

INSTITUTION
   │
   ├── LOCATION
   ├── TYPE
   └── RECOGNITION

ELIGIBILITY RULE
   │
   ├── PROGRAMME
   ├── INSTITUTION
   ├── ACADEMIC YEAR
   ├── QUALIFICATION
   ├── SUBJECTS
   ├── MARKS
   ├── ENTRANCE EXAM
   └── OTHER CONDITIONS
```

This separation is important because admission requirements can differ between institutions and academic years.

---

## 🛠️ Current Prototype

The current prototype focuses on the **graph interaction model**.

It demonstrates:

- Student as the root node
- Expandable education pathways
- MPC / BiPC / MEC / CEC / HEC
- Shared course possibilities
- Course detail panels
- Eligibility labels
- Institution-specific example constraints
- Search
- Zoom
- Pan

The current course data is **illustrative** and should not be treated as an official admission database.

---

## 🚧 Roadmap

### Phase 1 — Graph Architecture
- [x] Student root
- [x] Expand/collapse interaction
- [x] Network-style graph
- [x] Side information panel
- [x] Shared course concept

### Phase 2 — Education Catalogue
- [ ] Complete Intermediate pathways
- [ ] Complete Polytechnic pathways
- [ ] Complete ITI pathways
- [ ] Vocational pathways
- [ ] Undergraduate catalogue
- [ ] Postgraduate catalogue
- [ ] Research / PhD pathways
- [ ] Career and progression pathways

### Phase 3 — Eligibility Engine
- [ ] Qualification rules
- [ ] Subject requirements
- [ ] Marks requirements
- [ ] Entrance examinations
- [ ] Institution-specific constraints
- [ ] Academic-year rules
- [ ] Conditional eligibility
- [ ] Alternative pathways

### Phase 4 — Institution Database
- [ ] Universities
- [ ] Colleges
- [ ] Institutions
- [ ] Locations
- [ ] Programmes offered
- [ ] Admission rules
- [ ] Recognition information

### Phase 5 — Verification & Sources
- [ ] Official-source references
- [ ] Academic-year verification
- [ ] Rule versioning
- [ ] Last-verified dates
- [ ] Change tracking

### Phase 6 — Advanced Features
- [ ] Student profile builder
- [ ] Personalised pathway analysis
- [ ] Compare courses
- [ ] Compare institutions
- [ ] Missing-requirement explanations
- [ ] "What should I do next?" pathways
- [ ] Export/share pathway maps
- [ ] Mobile-responsive interface

---

## ⚠️ Data Accuracy

Education eligibility can depend on:

- Institution
- Programme
- Academic year
- State / admission authority
- Qualification board
- Subjects studied
- Marks
- Entrance examinations
- Applicable regulations

The framework should therefore **never present a generic rule as universally applicable when institution-specific rules differ**.

The long-term goal is to attach eligibility information to authoritative sources and record the relevant academic year/session.

---

## 🤝 Contributing

Contributions are welcome in areas such as:

- Adding education programmes
- Adding institutions
- Researching eligibility rules
- Improving graph visualisation
- Improving the eligibility engine
- Building data-import tools
- Improving accessibility
- Improving documentation

When adding eligibility information, provide the source and relevant academic year/session whenever possible.

---

## 📄 License

License information will be added when the project's licensing decision is finalized.

---

## 🌱 Project Vision

The long-term vision is to build an **interactive education knowledge graph** that helps a student answer:

> **"Given where I am now, what are all the possible education paths available to me, what are their requirements, which institutions offer them, and what can I do after completing each one?"**

The goal is not merely to recommend one course.

The goal is to make the **entire education landscape understandable and navigable**.
