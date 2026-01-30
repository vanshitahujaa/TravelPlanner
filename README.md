# Travel Itinerary AI Engine

A hybrid AI-powered itinerary generator that blends fuzzy logic, constraint satisfaction, A* search, and LLM-generated travel data into a transparent, personalized trip-planning engine. Produces day-by-day activity plans optimized for cost, travel time, user interests, and real-world constraints.

---

## 🌟 Overview

This engine combines traditional AI algorithms with structured LLM output to create fully optimized travel itineraries. Instead of relying on free-form suggestions, it integrates reasoning, validation, routing, and mutation-driven variation.

The system generates:

- Day-by-day itineraries  
- Flight and hotel recommendations  
- Full activity metadata  
- Transparent reasoning  
- Alternate itinerary variants  

---

## 🚀 Key Features

### **1. Structured LLM Data Generation**
The system requests and validates LLM-generated travel data:

- Flights  
- Hotels  
- 25–35 activities with:  
  - Coordinates  
  - Opening hours  
  - Cost  
  - Duration  
  - Popularity  

Strict JSON schema ensures reliability.

---

### **2. Fuzzy Logic Personalization**
Converts human-friendly pace descriptions:

- relaxed  
- moderate  
- fast  

into numeric scheduling parameters:

- max activities/day  
- downtime percentage  
- activity duration  
- travel buffer  

---

### **3. Constraint Satisfaction (CSP)**
Ensures plans meet user constraints:

- Budget (daily or total)  
- Must-visit places  
- Interest alignment  
- Time windows  
- Non-overlapping activities  

Violations are explicitly reported.

---

### **4. A* Search for Optimal Routing**
Builds daily activity order using:

- Travel distance minimization  
- Budget constraints  
- Daily time caps  
- Utility maximization  

**Utility formula:**

Utility = (AvgPopularity × 100) − (Cost × 0.1)

---

### **5. Genetic Mutation for Variation**
Generates alternate itineraries by mutating ~40% of activities:

- Category-aware replacements  
- Maintains theme & relevance  

Provides diverse itinerary options.

---

### **6. Transparent Reasoning**
Each output includes:

- Constraint analysis  
- Search strategy  
- Utility explanation  
- Fuzzy logic interpretation  
- State-vector signature  
- Any violations found  

---

## 🔍 System Architecture

User Preferences
│
▼
Fuzzy Logic → Pace Rules
│
▼
LLM Data Generation
│
▼
CSP Filtering → Budget / Interests / Must-Visit
│
▼
A* Search → Optimal Daily Routing
│
▼
Itinerary Assembly → Maps, Times, Costs
│
▼
Mutation Engine (optional)
│
▼
Final Itinerary + Reasoning

---

## ✨ Novelty / Differentiability

### **1. Hybrid Multi-AI Pipeline**
A rare integration of:

- Fuzzy logic  
- CSP  
- A*  
- Genetic mutation  
- Structured LLM output  

### **2. Hard Schema Validation**
Ensures activities have:

- Real numeric coordinates  
- Valid opening hours  
- Realistic costs  
- Popularity metrics  

### **3. Utility-Based Scheduling**
Algorithmically justifies why each activity is selected.

### **4. Deterministic State Vectors**
A hashed signature uniquely identifies itinerary versions.

### **5. Controlled Mutation Engine**
Allows flexible, controlled creativity in itinerary variations.

---

## 🧭 Ethical Considerations

### **1. Transparent Recommendations**
The system reveals:

- Constraints  
- Violations  
- Utility model  
- Reasoning  

### **2. User Autonomy**
Respect for:

- Budget limits  
- Must-visit places  
- Interests  
- Preferred pace  

### **3. Privacy-Safe**
No personal data is stored.  
Images are used only for local analysis.  
State vectors are hashed.

### **4. No Manipulative Biases**
- No affiliate prioritization  
- No forced bookings  
- Neutral recommendations  

### **5. Feasibility & Safety**
CSP prevents:

- impossible schedules  
- time-window violations  
- overspending  

---

## 📦 Installation

```bash
git clone <repository-url>
cd travel-itinerary-ai
npm install
🔧 Usage
Generate an Itinerary
import { generateItinerary } from "./generateItinerary";

const preferences = {
  destination: "Tokyo",
  origin: "Delhi",
  startDate: "2025-01-10",
  endDate: "2025-01-15",
  budget: 1200,
  interests: ["culture", "food", "nature"],
  pace: "moderate",
  tripType: "fullTrip",
  mustVisit: "Shinjuku Gyoen"
};

const itinerary = await generateItinerary(preferences);
console.log(JSON.stringify(itinerary, null, 2));
Mutate an Existing Itinerary
import { mutateItinerary } from "./generateItinerary";

const newVersion = await mutateItinerary(oldItinerary);
📄 License
MIT License.
# TravelPlanner

## AI Approach

This itinerary planner generates optimized, constraint-safe travel plans using:

- **Constraint Satisfaction Problem (CSP):** ensures feasibility of schedules  
- **A* Search:** optimizes routing between destinations  
- **Fuzzy Logic:** personalizes itinerary pace based on user preferences  

## Setup Instructions

```bash
git clone https://github.com/vanshitahujaa/TravelPlanner.git
cd TravelPlanner
pip install -r requirements.txt
python main.py