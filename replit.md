# SME Transaction Automation Platform (NYMO)

## Overview

This is a comprehensive SME (Small and Medium Enterprise) Transaction Automation Platform built for Indian businesses. The application integrates with Tally ERP to digitize end-to-end transaction workflows including sales, purchases, inventory management, and credit operations. It provides a modern web interface for managing quotations, orders, invoices, payments, and BNPL (Buy Now Pay Later) facilities while maintaining seamless synchronization with Tally accounting software.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript for type safety and modern development
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack React Query for server state management and caching
- **UI Components**: Radix UI primitives with custom styling for accessibility and consistency
- **Styling**: Tailwind CSS with a professional theme configuration using CSS custom properties
- **Build Tool**: Vite for fast development and optimized production builds

### Backend Architecture
- **Runtime**: Node.js with Express.js framework for RESTful API endpoints
- **Language**: TypeScript for type safety across the full stack
- **Architecture Pattern**: Layered architecture with controllers, services, and storage layers
- **API Design**: RESTful endpoints with proper HTTP status codes and error handling
- **Session Management**: Express sessions with PostgreSQL storage

### Database & ORM
- **Database**: PostgreSQL for robust relational data management
- **ORM**: Drizzle ORM for type-safe database operations and schema management
- **Schema**: Comprehensive schema covering users, parties (customers/vendors), items, transactions, BNPL limits, and Tally sync logs
- **Migrations**: Drizzle Kit for database schema migrations and version control
- **Connection**: Neon Database serverless PostgreSQL for cloud hosting

### Key Business Logic Components

#### Transaction Management
- **Transaction Types**: Sales invoices, purchase bills, quotations, orders, receipts, payments, debit/credit notes
- **Workflow Engine**: Status-based transaction progression (draft → pending → approved → completed)
- **Multi-currency Support**: Indian Rupee formatting with proper number localization
- **Aging Analysis**: Automatic calculation of receivables/payables aging buckets (0-30, 30-60, 60+ days)

#### BNPL Integration
- **Credit Scoring**: Dynamic credit limit calculation based on transaction history
- **Limit Tracking**: Real-time monitoring of used vs. available BNPL limits
- **Payment Options**: Integration with UPI, NEFT, RTGS, and card payments
- **Invoice Discounting**: Early payment discount mechanisms

#### Tally ERP Synchronization
- **Bidirectional Sync**: XML/ODBC integration for importing and exporting data
- **Conflict Resolution**: Manual override capabilities for data mismatches
- **Sync Logging**: Comprehensive audit trail of all synchronization activities
- **Data Mapping**: Automatic mapping between Tally ledgers and application entities

### External Dependencies

- **Database Hosting**: Neon Database for serverless PostgreSQL
- **Payment Processing**: Integration ready for Indian payment gateways (UPI, RTGS, NEFT)
- **Tally ERP Integration**: XML-based data exchange with Tally accounting software
- **Email/SMS Services**: Infrastructure for sending payment reminders and notifications
- **File Storage**: Support for document attachments and invoice PDFs
- **Authentication**: Session-based authentication with PostgreSQL session store

### Security & Performance
- **Type Safety**: Full TypeScript coverage from database to UI components
- **Input Validation**: Zod schemas for runtime type checking and validation
- **Error Handling**: Comprehensive error boundaries and API error responses
- **Performance**: Query optimization with TanStack Query caching and Vite build optimization
- **Responsive Design**: Mobile-first approach with adaptive layouts for desktop and mobile

### Development & Deployment
- **Hot Reload**: Vite HMR for rapid development iteration
- **Code Quality**: ESLint and TypeScript strict mode for code consistency
- **Build Process**: Optimized production builds with code splitting and tree shaking
- **Environment Management**: Environment-based configuration for database and external services