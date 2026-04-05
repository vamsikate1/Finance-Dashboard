# Finance Dashboard

A **React + TypeScript + Vite** finance dashboard for tracking balances, monthly cash flow, category spending, transactions (with role-based UI), and insights. Data is stored in **localStorage** in the browser (no backend required).

## Setup

```bash
npm install
npm run dev
```

Open the URL shown in the terminal (usually `http://localhost:5173`).

```bash
npm run build   # production build
npm run preview # serve dist locally
```

## How this meets the assignment

| Requirement | Implementation |
|-------------|----------------|
| **Dashboard overview** | Summary cards (balance, income, expenses), **Money flow** (time-based: income vs expense by month, range + bar/line + brush), **Expense categories over time** (line / stacked area, top-N categories), **Spending by category** (horizontal bars — categorical breakdown), **Balance trend** on Analytics. |
| **Transactions** | List with date, amount, category, **type** (income/expense badge), search, category/type/sort filters, **date range** filter. |
| **Role-based UI** | **Admin**: add / edit / delete, CSV import, mock API sync. **Viewer**: read-only. Switch role in Settings. |
| **Insights** | Highest spending category, month-over-month comparison, net position, budget health (linked to monthly budget). |
| **State** | `FinanceContext` holds transactions, filters, role, theme, budget, derived `filteredTransactions`. |
| **UI/UX** | Dark/light themes, responsive layout, collapsible sidebar on mobile, empty states on charts, toasts and confirm dialogs. |
| **Optional enhancements** | Dark mode, persistence, **mock API** sync, **export CSV/JSON**, **import CSV**, animations (Framer Motion on modals/toasts/confirms), advanced date filtering. |

## Features (quick tour)

- **Navigation**: Dashboard, Transactions, Analytics, Expenses, Settings.
- **Charts**: Toggle **6 / 12 / all months**, **bars vs trend lines**, **brush** on longer series; category chart **lines vs stacked area** and **3–6** top categories.
- **Budget**: Monthly target in Settings; progress on the dashboard and in insights.
- **Storage keys**: `finance-dashboard-*` (legacy `fundly-*` keys are migrated automatically once).

## Tech stack

- React 19, Vite, TypeScript, Tailwind CSS v4, Recharts, Lucide icons, Framer Motion.

## Assumptions

- Amounts are **USD**; expenses are stored as **negative** values internally.
- “Mock API” returns the built-in seed dataset with new ids after a short delay (demonstration only).
