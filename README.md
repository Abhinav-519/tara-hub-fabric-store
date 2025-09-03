# Tara Hub Fabric Store

A modern e-commerce platform for browsing and purchasing fabric samples, built with Next.js 15 and React 19.

## Features

- 🎨 Beautiful fabric browsing experience
- 🛒 Shopping cart and wishlist functionality
- 🔐 Authentication with Google OAuth and Phone OTP
- 📱 Fully responsive design
- 🎯 Advanced filtering and search
- 💳 Stripe payment integration
- 📦 Order management

## Tech Stack

- **Framework**: Next.js 15 with App Router
- **UI**: Tailwind CSS + Radix UI components
- **Authentication**: NextAuth.js
- **Payments**: Stripe
- **SMS**: Twilio (for OTP)
- **Backend**: Medusa.js (optional)

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn
- Twilio account (for OTP)
- Google OAuth credentials
- Stripe account

### Installation

1. Clone the repository:
```bash
git clone https://github.com/varaku1012/tara-hub-fabric-store.git
cd tara-hub-fabric-store
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
cp .env.example .env.local
```

Edit `.env.local` with your credentials:
```env
# Authentication
NEXTAUTH_URL=http://localhost:3006
NEXTAUTH_SECRET=your-secret-key
JWT_SECRET=your-jwt-secret

# Google OAuth
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

# Twilio (for OTP)
TWILIO_ACCOUNT_SID=your-account-sid
TWILIO_AUTH_TOKEN=your-auth-token
TWILIO_PHONE_NUMBER=your-twilio-number

# Stripe
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your-stripe-pk
STRIPE_SECRET_KEY=your-stripe-sk

# Medusa Backend (optional)
NEXT_PUBLIC_MEDUSA_BACKEND_URL=http://localhost:9000
```

4. Run the development server:
```bash
npm run dev
```

Open [http://localhost:3006](http://localhost:3006) to see the application.

## Project Structure

```
├── app/                    # Next.js app router pages
│   ├── api/               # API routes
│   ├── auth/              # Authentication pages
│   ├── browse/            # Product browsing
│   ├── cart/              # Shopping cart
│   └── checkout/          # Checkout flow
├── components/            # React components
│   ├── ui/               # UI components
│   └── providers/        # Context providers
├── hooks/                # Custom React hooks
├── lib/                  # Utility functions
└── public/              # Static assets
```

## Key Features

### Authentication
- Google OAuth sign-in
- Phone number OTP authentication
- Session management with NextAuth.js

### Product Browsing
- Grid/list view toggle
- Advanced filtering (category, price, color)
- Search functionality
- Product quick view

### Shopping Experience
- Add to cart/wishlist
- Cart management
- Checkout with Stripe
- Order history

## Deployment

### Vercel (Recommended)

1. Push to GitHub
2. Import project in Vercel
3. Configure environment variables
4. Deploy

### Docker

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build
EXPOSE 3006
CMD ["npm", "start"]
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License.

## Support

For support, email admin@tara-hub.com or open an issue on GitHub.
