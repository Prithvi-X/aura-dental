# Aura Dental

A full-stack dental clinic web platform built to handle patient discovery, treatment estimation, consultation booking, payments, and internal booking management.

## Overview

Aura Dental is a production-style dental clinic platform focused on making the patient journey simple while giving the clinic an internal system to manage bookings and leads.

The project includes both a public-facing patient experience and a protected admin workflow.

## What I Built

### Patient Experience

- Premium responsive dental clinic website
- Treatment discovery and service browsing
- Treatment price estimator
- Lead capture through the treatment estimator
- Multi-step consultation booking flow
- Treatment selection and preferred consultation time
- Patient details collection
- Online deposit/payment flow
- Booking confirmation flow
- WhatsApp contact integration
- Mobile-friendly navigation and CTAs
- Testimonials, reviews, FAQs and treatment information

### Booking & Payments

- Multi-step booking wizard
- Stripe PaymentIntent integration
- Payment webhook processing
- Booking creation after successful payment authorization
- Unique booking references
- Booking lifecycle/status management
- Duplicate payment protection through unique payment intent IDs

### Internal Admin System

- Protected staff/admin login
- Booking dashboard
- Booking statistics
- Search and filtering
- Booking status management
- Consultation date/time management
- Internal admin notes
- Treatment estimate lead management
- Payment cancellation/refund workflow

### Data & Communication

- Supabase-backed booking and lead storage
- Row Level Security policies for authenticated admin access
- Transactional emails using Resend
- Google Analytics event tracking
- Structured API routes for booking, payment and administrative operations

## Tech Stack

- Next.js 16
- React 19
- TypeScript
- Tailwind CSS
- Framer Motion
- Supabase
- Stripe
- Resend
- React Hook Form
- Zod
- Vercel

## Architecture

```text
                    ┌─────────────────────┐
                    │   Patient Website   │
                    │ Next.js + React     │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
       Treatment        Booking System     Estimate Lead
       Estimator             │                │
                             ▼                ▼
                        API Routes         Supabase
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
                 Stripe            Supabase
                 Payments          Database
                    │
                    ▼
             Stripe Webhooks
                    │
                    ▼
              Booking Creation
                    │
                    ▼
             Resend Email Flow

                    ──────────────────

                    Admin Dashboard
                          │
                          ▼
                       Supabase
                          │
              ┌───────────┼───────────┐
              ▼           ▼           ▼
           Bookings     Leads      Statistics
