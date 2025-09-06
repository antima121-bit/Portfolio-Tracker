# 🔄 Portfolio Dashboard  
📊 A full-stack portfolio tracking app with **real-time stock data, analytics, and insights**.

![Next.js](https://img.shields.io/badge/Next.js-14-black?style=flat-square&logo=nextdotjs)
![Supabase](https://img.shields.io/badge/Supabase-Backend-green?style=flat-square&logo=supabase)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue?style=flat-square&logo=postgresql)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

# 🔄 Portfolio Dashboard  

[![Live Demo](https://img.shields.io/badge/Demo-Vercel-green?style=for-the-badge&logo=vercel)](https://portfolio-tracker-green.vercel.app/)
[![GitHub Repo](https://img.shields.io/badge/Repo-GitHub-black?style=for-the-badge&logo=github)](https://github.com/antima121-bit/Portfolio-Tracker)

### Portfolio Dashboard
<img width="1880" height="933" alt="image" src="https://github.com/user-attachments/assets/f8d04e91-f2c5-4f67-b29e-3370763fb04c" />
<img width="1487" height="912" alt="image" src="https://github.com/user-attachments/assets/22e53f3c-3133-4cae-94b9-fba303e1698e" />
<img width="1416" height="960" alt="image" src="https://github.com/user-attachments/assets/7d1156f6-5916-4b5a-9a8d-b02f1014bb23" />
<img width="1327" height="585" alt="image" src="https://github.com/user-attachments/assets/88787b40-35a8-456a-a0d4-76053166b7a1" />
<img width="1307" height="592" alt="image" src="https://github.com/user-attachments/assets/ae30e85e-3817-4f21-9835-f038c4718732" />
<img width="1252" height="651" alt="image" src="https://github.com/user-attachments/assets/b0b3e0e2-2f37-447a-8daf-408551cf8252" />
<img width="1298" height="710" alt="image" src="https://github.com/user-attachments/assets/29e08ce6-2584-4304-99a1-d670b30e9534" />


> The dashboard shows **total investment, current value, gain/loss, holdings, sector performance, and portfolio allocation** at a glance.



## System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend       │    │   Database      │
│   (Next.js)     │◄──►│   (Supabase)    │◄──►│   (PostgreSQL)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   UI Components │    │   API Routes    │    │   Data Tables   │
│   - Dashboard   │    │   - /api/portfolio│    │   - sectors     │
│   - Analytics   │    │   - /api/sectors │    │   - stocks      │
│   - Charts      │    │   - /api/stocks  │    │   - holdings    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 📑 Table of Contents
1. [System Architecture](#system-architecture)
2. [Data Flow Workflow](#data-flow-workflow)
3. [Technology Stack](#technology-stack-workflow)
4. [Component Architecture](#component-architecture)
5. [API Architecture](#api-architecture)
6. [Database Schema](#database-schema-workflow)
7. [Security](#security-workflow)
8. [Deployment](#deployment-workflow)
9. [Performance Optimizations](#performance-optimizations)
10. [Monitoring & Analytics](#monitoring--analytics)
11. [Development Workflow](#development-workflow)
12. [Future Enhancements](#future-enhancements)

## Data Flow Workflow

### 1. **Initial Load**
```
User Opens App → Authentication Check → Load Dashboard → Fetch Portfolio Data
```

### 2. **Real-time Updates**
```
Stock Price API → Update Database → Trigger Re-render → Update UI Components
```

### 3. **Analytics Processing**
```
Portfolio Data → Calculate Metrics → Generate Charts → Display Insights
```

## Technology Stack Workflow

### **Frontend Layer**
- **Next.js 14** - React framework with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Styling and responsive design
- **Radix UI** - Accessible component primitives
- **Recharts** - Data visualization and charts

### **Backend Layer**
- **Supabase** - Backend-as-a-Service
- **PostgreSQL** - Relational database
- **Row Level Security** - Data access control
- **Real-time Subscriptions** - Live updates

### **Data Layer**
- **Stock Data Providers** - Yahoo Finance & Google Finance
- **Mock Data Generation** - Realistic market simulation
- **Price Update Service** - Real-time price synchronization

## Component Architecture

### **Dashboard Components**
```
DashboardLayout
├── PortfolioSummary
├── SectorPerformanceChart
├── PortfolioTable
└── SectorAnalysis
```

### **Analytics Components**
```
AnalyticsPage
├── PortfolioPerformanceChart
├── RiskAnalysis
├── TopPerformers
├── DiversificationMetrics
├── MarketCorrelation
└── PortfolioInsights
```

## API Architecture

### **Portfolio API** (`/api/portfolio`)
- **GET** - Fetch portfolio holdings with real-time prices
- **POST** - Add new portfolio holdings
- **Authentication** - User-specific data access

### **Sectors API** (`/api/sectors`)
- **GET** - Fetch sector-wise portfolio breakdown
- **Real-time** - Live sector performance metrics
- **Aggregation** - Calculate sector totals and percentages

### **Stock Prices API** (`/api/stocks/prices`)
- **GET** - Update stock prices from external providers
- **POST** - Manual price updates
- **Real-time** - 15-second update intervals

## Database Schema Workflow

### **Core Tables**
1. **`sectors`** - Investment sectors
2. **`stocks`** - Stock information
3. **`portfolio_holdings`** - User positions
4. **`stock_prices`** - Real-time prices

### **Relationships**
```
sectors (1) ←→ (many) stocks
stocks (1) ←→ (many) portfolio_holdings
stocks (1) ←→ (1) stock_prices
```

## Security Workflow

### **Authentication Flow**
```
User Login → Supabase Auth → JWT Token → Protected Routes
```

### **Data Security**
```
API Request → RLS Check → User Authorization → Data Access
```

## Deployment Workflow

### **Development**
```
Local Development → Git Commit → GitHub Push → Vercel Deploy
```

### **Production**
```
Vercel Build → Environment Variables → Database Connection → Live App
```

## Performance Optimizations

### **Frontend**
- **Code Splitting** - Lazy loading components
- **Image Optimization** - Next.js image optimization
- **Caching** - Browser and CDN caching
- **Bundle Optimization** - Tree shaking and minification

### **Backend**
- **Database Indexing** - Optimized queries
- **Connection Pooling** - Efficient database connections
- **Caching** - Redis caching for frequently accessed data
- **CDN** - Global content delivery

## Monitoring & Analytics

### **Application Monitoring**
- **Vercel Analytics** - Performance metrics
- **Error Tracking** - Error boundaries and logging
- **User Analytics** - Usage patterns and behavior

### **Database Monitoring**
- **Supabase Dashboard** - Database performance
- **Query Optimization** - Slow query identification
- **Connection Monitoring** - Database health checks

## Development Workflow

### **Local Development**
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run lint         # Code quality checks
npm run type-check   # TypeScript validation
```

### **Testing Strategy**
- **Unit Tests** - Component testing
- **Integration Tests** - API testing
- **E2E Tests** - User journey testing
- **Performance Tests** - Load testing

## Future Enhancements

### **Planned Features**
- **Mobile App** - React Native version
- **AI Insights** - Machine learning predictions
- **Social Features** - Portfolio sharing
- **Advanced Analytics** - More sophisticated metrics
- **Multi-Currency** - International support
- **Tax Reporting** - Capital gains calculations

### **Technical Improvements**
- **Microservices** - Service-oriented architecture
- **GraphQL** - More efficient data fetching
- **WebSockets** - Real-time bidirectional communication
- **PWA** - Progressive web app features
- **Offline Support** - Service worker implementation

- ## 📬 Contact
- **Author**: [Antima Mishra](https://github.com/antima121-bit)  
- **Email**: antimamishra113@gmail.com  
- **LinkedIn**: [Your Profile](https://www.linkedin.com/in/antima-mishra-6483ba252/)  
 Vercel Demo Link: https://portfolio-tracker-green.vercel.app/


