# Resources for E-commerce Store

## 📺 Video Tutorials
- [Build a Modern E-commerce Store with Next.js 15 & Tailwind](https://www.youtube.com/watch?v=5miHyP6lExg) - Code with Antonio: Complete tutorial (2025/2026 edition)
- [Full Stack E-commerce App with Next.js, Prisma & Stripe](https://www.youtube.com/watch?v=EGcPg_1U-J4) - JavaScript Mastery: Modern MERN-style implementation
- [Stripe Payment Integration with Next.js 15](https://www.youtube.com/watch?v=1r-F3FIONl8) - Web Dev Simplified: Stripe setup and checkout
- [Next.js Commerce 2026 – Enterprise Patterns](https://www.youtube.com/watch?v=I1cpb0tYV74) - Vercel: Official enterprise e-commerce patterns

## 📚 Written Tutorials
- [Build an E-commerce App with Next.js 15 and Stripe](https://www.freecodecamp.org/news/create-an-ecommerce-site-with-nextjs-and-stripe/) - freeCodeCamp guide (updated 2026)
- [Stripe Payment Tutorial](https://stripe.com/docs/payments/quickstart) - Official Stripe documentation
- [E-commerce Database Design with Prisma](https://medium.com/@kimtnguyen/designing-a-relational-database-for-an-e-commerce-website-ba5c233ae050) - Database schema guide (updated)
- [Shopping Cart with React & Zustand](https://www.robinwieruch.de/react-shopping-cart/) - Cart state management (2026 edition)

## 🔧 Tools & Libraries

### Payment Processing
- [Stripe](https://stripe.com/) - Payment processing platform - **RECOMMENDED**
- [PayPal SDK](https://developer.paypal.com/sdk/js/) - PayPal integration
- [Razorpay](https://razorpay.com/) - Payment gateway for India
- [Square](https://developer.squareup.com/) - Alternative payment processor

### E-commerce Frameworks
- [Medusa](https://medusajs.com/) - Open-source Shopify alternative
- [Saleor](https://saleor.io/) - Headless GraphQL e-commerce
- [Commerce.js](https://commercejs.com/) - Headless e-commerce API
- [Shopify Buy SDK](https://shopify.dev/api/storefront) - Connect to Shopify backend

### State Management
- [Zustand](https://github.com/pmndrs/zustand) - Lightweight cart state management
- [Redux Toolkit](https://redux-toolkit.js.org/) - Complex state management
- [TanStack Query](https://tanstack.com/query/latest) - Server state management

### Email Services
- [Resend](https://resend.com/) - Modern email API for developers - **RECOMMENDED**
- [SendGrid](https://sendgrid.com/) - Email delivery service
- [Nodemailer](https://nodemailer.com/) - Email sending library
- [React Email](https://react.email/) - Beautiful email templates with React

## 💻 GitHub Repositories
- [Next.js Commerce](https://github.com/vercel/commerce) - Official Vercel e-commerce template
- [Medusa Starter](https://github.com/medusajs/nextjs-starter-medusa) - Next.js + Medusa
- [React E-commerce](https://github.com/jeffersonRibeiro/react-shopping-cart) - Complete React example
- [MERN E-commerce](https://github.com/basir/amazona) - Full-stack MERN implementation
- [Shopify Next.js](https://github.com/vercel/nextjs-commerce-shopify) - Shopify integration

## 📖 Learning Resources

### E-commerce Fundamentals
- [E-commerce UX Best Practices](https://baymard.com/blog) - Baymard Institute research
- [Checkout Optimization](https://cxl.com/blog/checkout-optimization/) - Conversion optimization
- [Product Page Design](https://www.smashingmagazine.com/2020/02/design-ecommerce-product-page/) - Smashing Magazine guide

### Payment Integration
- [Stripe Documentation](https://stripe.com/docs) - Complete Stripe guide
- [Stripe Checkout](https://stripe.com/docs/payments/checkout) - Pre-built checkout page
- [Payment Intents API](https://stripe.com/docs/payments/payment-intents) - Custom payment flows
- [PCI Compliance Guide](https://stripe.com/docs/security/guide) - Security best practices

### Database Design
- [E-commerce Database Schema](https://www.vertabelo.com/blog/designing-a-database-for-an-online-shop/) - Schema design patterns
- [Prisma E-commerce Schema](https://www.prisma.io/docs/guides/database/advanced-database-tasks/cascading-deletes) - Prisma examples
- [Inventory Management](https://www.techtarget.com/searcherp/definition/inventory-management) - Inventory concepts

## 🌐 APIs & Services
- [Stripe API](https://stripe.com/docs/api) - Payment processing (free for testing)
- [PayPal SDK](https://developer.paypal.com/home) - Alternative payment gateway
- [Shippo API](https://goshippo.com/) - Shipping label generation
- [TaxJar API](https://www.taxjar.com/api/) - Sales tax calculation
- [Google Maps API](https://developers.google.com/maps) - Address autocomplete

## 🎨 Design Resources
- [E-commerce UI Kits](https://dribbble.com/search/ecommerce) - Dribbble inspiration
- [Shopify Polaris](https://polaris.shopify.com/) - Design system for commerce
- [Product Page Examples](https://www.awwwards.com/websites/e-commerce/) - Award-winning designs
- [Figma E-commerce Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=ecommerce) - Free templates

## 📚 Shopping Cart State Example
```typescript
// Zustand cart store
import { create } from 'zustand';
import { persist } from 'zustand/middleware';

interface CartItem {
  id: string;
  name: string;
  price: number;
  quantity: number;
  image: string;
}

interface CartStore {
  items: CartItem[];
  addItem: (item: CartItem) => void;
  removeItem: (id: string) => void;
  updateQuantity: (id: string, quantity: number) => void;
  clearCart: () => void;
  total: () => number;
}

export const useCart = create<CartStore>()(
  persist(
    (set, get) => ({
      items: [],
      addItem: (item) =>
        set((state) => {
          const existing = state.items.find((i) => i.id === item.id);
          if (existing) {
            return {
              items: state.items.map((i) =>
                i.id === item.id ? { ...i, quantity: i.quantity + 1 } : i
              ),
            };
          }
          return { items: [...state.items, { ...item, quantity: 1 }] };
        }),
      removeItem: (id) =>
        set((state) => ({
          items: state.items.filter((i) => i.id !== id),
        })),
      updateQuantity: (id, quantity) =>
        set((state) => ({
          items: state.items.map((i) =>
            i.id === id ? { ...i, quantity } : i
          ),
        })),
      clearCart: () => set({ items: [] }),
      total: () =>
        get().items.reduce((sum, item) => sum + item.price * item.quantity, 0),
    }),
    { name: 'cart-storage' }
  )
);

### 💳 Stripe Integration Example

// Server-side checkout session creation
import Stripe from 'stripe';
const stripe = new Stripe(process.env.STRIPE_SECRET_KEY);

export async function createCheckoutSession(items: CartItem[]) {
  const session = await stripe.checkout.sessions.create({
    payment_method_types: ['card'],
    line_items: items.map((item) => ({
      price_data: {
        currency: 'usd',
        product_data: {
          name: item.name,
          images: [item.image],
        },
        unit_amount: item.price * 100, // Stripe uses cents
      },
      quantity: item.quantity,
    })),
    mode: 'payment',
    success_url: `${process.env.NEXT_PUBLIC_URL}/success?session_id={CHECKOUT_SESSION_ID}`,
    cancel_url: `${process.env.NEXT_PUBLIC_URL}/cart`,
  });

  return session;
}

### 📊 Database Schema Example (Prisma)

model Product {
  id          String   @id @default(cuid())
  name        String
  description String
  price       Float
  images      String[]
  category    Category @relation(fields: [categoryId], references: [id])
  categoryId  String
  stock       Int      @default(0)
  orders      OrderItem[]
  reviews     Review[]
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
}

model Order {
  id            String      @id @default(cuid())
  userId        String
  user          User        @relation(fields: [userId], references: [id])
  items         OrderItem[]
  total         Float
  status        OrderStatus @default(PENDING)
  shippingAddress Json
  paymentIntent String      @unique
  createdAt     DateTime    @default(now())
}

model OrderItem {
  id        String  @id @default(cuid())
  orderId   String
  order     Order   @relation(fields: [orderId], references: [id])
  productId String
  product   Product @relation(fields: [productId], references: [id])
  quantity  Int
  price     Float
}

enum OrderStatus {
  PENDING
  PROCESSING
  SHIPPED
  DELIVERED
  CANCELLED
}

### 📧 Order Confirmation Email

// Using React Email
import { Html, Button, Section, Text } from '@react-email/components';

export function OrderConfirmation({ order }) {
  return (
    <Html>
      <Section>
        <Text>Thank you for your order #{order.id}!</Text>
        <Text>Total: ${order.total}</Text>
        <Button href={`https://yourstore.com/orders/${order.id}`}>
          Track Order
        </Button>
      </Section>
    </Html>
  );
}
