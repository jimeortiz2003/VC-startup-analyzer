# VC Startup Analyzer

A data-driven tool to evaluate early-stage startups for investment readiness, tailored for aspiring venture capitalists, analysts, and anyone passionate about startup ecosystems.

## Problem Statement
Early-stage investors face information overload and inconsistency when screening startups. This tool helps evaluate investment potential based on key indicators such as funding history, team composition, market size, and traction—using open-source or scraped datasets (e.g., Crunchbase).

## Project Goals
- Identify and clean relevant startup data
- Analyze and visualize trends in funding, sectors, and startup metrics
- Develop a **VC Fit Score**: a composite score based on criteria like market, traction, and team
- Optional: Build a user-friendly dashboard using Streamlit

## Key Features
- Python-based data wrangling and EDA
- Scoring model: `VC Fit Score`
- Industry filters, stage segmentation, and ranking
- Optional Tableau/Streamlit interface for interactive exploration

## Skills Demonstrated
- Data cleaning and transformation (pandas, numpy)
- Visualization (matplotlib, seaborn, plotly)
- Scoring logic and model thinking
- Understanding of VC evaluation metrics
- Optional: dashboard design with Streamlit

## File Overview
| File/Folder | Description |
|-------------|-------------|
| `data/` | Startup data (raw + cleaned) |
| `notebooks/` | Jupyter notebooks for exploration and scoring |
| `src/` | Python scripts for cleaning and scoring |
| `dashboard/` | Optional Streamlit or Tableau app |
| `outputs/` | Summary report or visuals for sharing |

## Tech Stack
- Python (pandas, numpy, matplotlib, seaborn, sklearn)
- Optional: Streamlit or Tableau
- Data source: Public Crunchbase export or mock data

## Future Enhancements
- Integrate scraping tool for live data
- Add filters for region/industry/investor type
- NLP on pitch descriptions or market tags
- Predictive funding success model

## Created by **Jimena Ortiz** | Business Analytics + Finance | VC & Fintech Enthusiast  
