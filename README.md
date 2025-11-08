# KisanConnect 2.0

A modern, full-stack agricultural platform built for Nepali farmers to access real-time market data, weather forecasts, government subsidies, and agricultural learning resources.

## Features

### For Farmers
- **Crop Marketplace** - List and sell crops directly to buyers
- **Market Prices** - Real-time hourly market price updates
- **Weather Forecast** - 7-day forecast with alerts for frost/rain
- **Dashboard** - Track earnings, crops, and orders
- **Subsidies** - Find and apply for government subsidies
- **Learning** - Step-by-step guides for organic, mushroom, dairy, and greenhouse farming

### For Buyers
- **Browse Marketplace** - Search and filter available crops
- **Order Management** - Track orders and payments
- **Farmer Directory** - Connect directly with farmers

### For Admins
- **User Management** - Manage all platform users
- **Content Management** - Update news, learning modules, subsidies
- **Analytics** - Platform metrics and insights
- **Moderation** - Review and approve listings

## Tech Stack

- **Frontend**: Next.js 15, React 19, Tailwind CSS
- **Backend**: Node.js, Express, MongoDB
- **Authentication**: JWT with role-based access control
- **Real-time Updates**: Cron jobs for hourly data updates
- **Deployment**: Vercel

## Getting Started

### Prerequisites
- Node.js 18+
- MongoDB Atlas account
- Environment variables configured

### Installation

1. Clone the repository
2. Install dependencies: `npm install`
3. Set up environment variables from `.env.example`
4. Initialize database: `npm run init-db`
5. Seed data: `npm run seed`
6. Start development: `npm run dev`

### Deployment

This project is fully deployable on Vercel with automatic environment variable handling.

## Database Schema

See `scripts/mongodb-schema.json` for complete data structure including Users, Crops, Orders, Market Prices, Weather, News, Learning, Subsidies, and Insurance collections.

## API Endpoints

- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `GET /api/crops` - List all crops
- `POST /api/crops` - Add new crop (authenticated)
- `GET /api/market-prices` - Get market prices
- `GET /api/weather` - Get weather forecast
- `GET /api/news` - Get agricultural news
- `GET /api/subsidies` - Get available subsidies
- `POST /api/cron/market-prices` - Update market prices (cron)
- `POST /api/cron/news` - Update news (cron)

## Contributing

Contributions are welcome! Please follow the existing code structure and add tests for new features.

## License

MIT

## Support

For issues and support, visit: https://github.com/kisan-connect/issues
