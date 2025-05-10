# 🎬 Movie Recommendation System using SARSA

This project implements a **content-based movie recommendation system** using the **SARSA Reinforcement Learning algorithm**. It is based on user interactions (ratings) and their preferred genres.

---

## 🚀 Objectives

- Recommend **movies the user has never seen**
- Use SARSA to learn a **recommendation policy**
- Take into account **preferred genres** (from ratings ≥ 3.0)
- Optimize **simulated click rewards**

---

## 🧠 Technologies

- `Python`
- `NumPy`, `Pandas`
- `Matplotlib`, `Seaborn`
- `tqdm` (for progress tracking)
- `SARSA` (tabular reinforcement learning)

---

## 📁 Project Structure

📦 recommendation-sarsa
┣ 📄 recommender_sarsa.py # Main code (training + recommendation)
┣ 📄 merged_movie_data.csv # Dataset (userId, movieId, title, rating, genres)

---

## 📊 Dataset

The file `merged_movie_data.csv` contains:

- `userId`: user identifier
- `movieId`: movie identifier
- `title`: movie title
- `rating`: user's rating (from 0.5 to 5.0)
- `genres`: movie genres (separated by "|")

---

## 🔀 Code Versions

### 1. `Recommandation_Sarsa_V1.ipynb`
> Works with a filtered dataset containing **only the top 20 users and top 50 movies**.  
Ideal for faster experimentation and debugging with a smaller Q-table.

### 2. `Recommandation_Sarsa_V2.ipynb`
> Uses **the complete dataset**.  
Trains the agent to recommend movies across **all users**, considering only **unseen movies**, and factoring in **genre preferences** based on movies rated ≥ 3.0.

---

## ⚙️ How It Works

1. Builds a Q-table: `Q[user, movie]`
2. For each episode:
   - For each user:
     - Select a movie they haven’t seen yet (explore/exploit)
     - Compute reward:
       - +1 if rating ≥ 3.0
       - + genre similarity with user preferences
     - Update the Q-table using SARSA
3. At the end: a personalized movie recommendation is generated for each user.

---

## 📈 Visualization

The script plots the cumulative reward over episodes (weighted clicks) to visualize the model’s learning progress.

---

## 🧪 Example Output

User 12 → Recommended: The Matrix (1999)
User 17 → Recommended: Forrest Gump (1994)

