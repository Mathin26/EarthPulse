# EarthPulse — Global Impact Platform

A real-time climate impact tracking platform with AI-powered insights. EarthPulse aggregates global climate data, provides intelligent retrieval-augmented generation (RAG) responses, and helps users understand interconnected environmental crises through a social feed of climate alerts and scientific findings.

## 🌍 Overview

EarthPulse is a web-based platform that combines:
- **Real-time impact tracking** — Monitor critical climate indicators (CO₂, temperature, sea level rise, biodiversity loss)
- **RAG-powered AI insights** — Query a knowledge base of 120+ peer-reviewed climate documents with AI-generated context
- **Vector search** — Semantic similarity matching across climate domains
- **Social feed** — Crowdsourced climate alerts tagged by impact severity
- **Graph analysis** — PageRank-based post ordering to surface critical information

## 🏗️ Architecture

```
EarthPulse/
├── EarthPulse.API          # ASP.NET Core Web API + SignalR hubs
├── EarthPulse.Core         # Domain entities, services, interfaces
├── EarthPulse.Infrastructure  # Data repositories, vector store, AI services
└── EarthPulse.Tests        # MOQ unit tests (C# v8.0, Moq v4.20)
```

### Key Components

- **RAG Service** — Retrieves relevant climate documents, augments user queries with context, generates AI responses
- **Vector Store** — In-memory cosine similarity search over climate document embeddings
- **Post Service** — Manages user-submitted climate alerts and impact assessments
- **PageRank Engine** — Graph-based ranking to prioritize posts by interconnected impact
- **SignalR Hub** — Real-time broadcast of critical alerts

## 📊 Knowledge Base

Comprehensive 120+ document knowledge base covering:
- **Global Warming** — CO₂ levels, temperature anomalies, tipping points, extreme weather
- **Oceans** — Acidification, deoxygenation, coral bleaching
- **Biodiversity** — Species extinction rates, habitat loss, invasive species
- **Pollution** — Air quality, plastic waste, chemical contamination
- **Energy** — Renewable transition, fossil fuel economics, energy access
- **Water** — Freshwater depletion, groundwater contamination, dam impacts
- **Food Security** — Crop yields, agricultural emissions, nutrition
- **Social Impact** — Climate migration, health effects, climate anxiety

All documents include peer-reviewed sources and quantitative impact metrics.

## 🛠️ Tech Stack

- **Backend:** ASP.NET Core (C# 8.0+)
- **Testing:** MOQ v4.20, xUnit
- **Real-time:** SignalR
- **AI/Embeddings:** OpenAI (external integration)
- **Frontend:** Vanilla HTML/CSS/JavaScript (single-page app)
- **Data:** In-memory vector store with cosine similarity

## ✅ Testing Approach (MOQ)

Unit tests mock key dependencies:
- `IVectorStore` — Mocked for vector search verification
- `IAIService` — Mocked for embedding and generation calls
- `IPostRepository` — Mocked for data persistence
- `ISignalRGroupManager` — Mocked for real-time alerts

Run tests:
```bash
dotnet test EarthPulse.Tests --verbosity normal
```

## 🚀 Getting Started

### Prerequisites
- .NET 8.0 SDK
- OpenAI API key (for embeddings and generation)

### Setup
1. Clone the repository
2. Configure OpenAI credentials in `appsettings.json`
3. Build the solution:
   ```bash
   dotnet build EarthPulse.sln
   ```
4. Run tests:
   ```bash
   dotnet test EarthPulse.Tests
   ```
5. Start the API:
   ```bash
   dotnet run --project EarthPulse.API
   ```
   - API runs on `https://localhost:7241`
   - SignalR hub available at `/hubs/impact`

## 📈 Key Features

✓ Real-time climate indicators with live updates  
✓ Vector-based semantic search over 120+ climate documents  
✓ RAG-powered AI responses grounded in scientific literature  
✓ Social feed with severity-tagged climate alerts  
✓ Graph-based impact ranking (PageRank algorithm)  
✓ Comprehensive MOQ unit test coverage (9+ test suites)  

## 📚 Data Sources

All knowledge documents backed by:
- IPCC Assessment Reports (AR6)
- NOAA, NASA, WMO official data
- Peer-reviewed journals (Nature, Science, PNAS)
- WHO, FAO, IEA reports
- Global Forest Watch, World Bank

## 📝 License

University Project — Educational Use Only

---

**EarthPulse — Tracking Global Impact in Real-Time**
