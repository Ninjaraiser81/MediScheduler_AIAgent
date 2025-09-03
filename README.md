# MediScheduler_AIAgent

# MediScheduler: Intelligent Medical Appointment Scheduling

MediScheduler is a modern, AI-powered web application designed to simplify medical appointment scheduling. It leverages artificial intelligence to suggest optimal appointment times, provides a comprehensive dashboard for tracking monthly analytics, and allows for seamless management of appointment details.

This project was built with Next.js, Firebase Studio, and Google's Genkit.

## Key Features

- **AI-Powered Scheduling:** Utilizes AI to analyze doctor and patient availability, suggesting the most suitable appointment slots to minimize conflicts and maximize efficiency.
- **Interactive Dashboard:** A central hub to view all appointments, with an AI-generated monthly report that provides insights into key metrics like total appointments, peak days, and doctor-specific analytics.
- **Dynamic Calendar:** A full-featured calendar to navigate through dates and view scheduled appointments.
- **Appointment Management:** Easily view appointment details, update their status (Upcoming, Completed, Cancelled), and print a PDF summary for any appointment.
- **Responsive Design:** A clean, modern, and fully responsive user interface built with ShadCN UI and Tailwind CSS, ensuring a great experience on any device.
- **Customizable Settings:** A dedicated page for users to manage their profile and scheduling preferences.

## Tech Stack

- **Framework:** [Next.js](https://nextjs.org/) (with App Router)
- **Language:** [TypeScript](https://www.typescriptlang.org/)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **UI Components:** [ShadCN UI](https://ui.shadcn.com/)
- **AI/Generative:** [Genkit (with Google Gemini)](https://firebase.google.com/docs/genkit)
- **State Management:** [Zustand](https://github.com/pmndrs/zustand)
- **Charts:** [Recharts](https://recharts.org/)
- **Icons:** [Lucide React](https://lucide.dev/)

## Project Structure

The project follows a standard Next.js App Router structure:

-   `src/app/`: Contains the main application pages and layouts.
    -   `(app)/`: A route group for the main authenticated pages (Dashboard, Schedule, Settings).
    -   `globals.css`: Global styles and Tailwind CSS theme configuration.
    -   `layout.tsx`: The root layout for the entire application.
-   `src/ai/`: Home for all AI-related logic.
    -   `flows/`: Contains the Genkit flows that define the AI agents and their capabilities.
    -   `genkit.ts`: Configures and initializes the Genkit AI instance.
-   `src/components/`: Shared React components used across the application.
    -   `layout/`: Components specific to the main app layout (e.g., Sidebar, Logo).
    -   `ui/`: Reusable UI components from `shadcn/ui` (e.g., Button, Card).
-   `src/hooks/`: Custom React hooks, such as `useToast` for notifications.
-   `src/lib/`: Utility functions, including `cn` for merging Tailwind classes.
-   `src/store/`: Contains the Zustand store for global client-side state management of appointments.
-   `public/`: Static assets.

## AI Integration

This application uses **Genkit** to integrate with Google's Gemini models for its intelligent features. The AI flows are defined in the `src/ai/flows/` directory and handle tasks such as:
- `generate-initial-schedule-options.ts`: Takes patient and doctor availability, meeting duration, and timezone to suggest three optimal appointment slots with suitability scores.
- `generate-monthly-analytics.ts`: Analyzes a list of appointments for a given month and generates a comprehensive report including total appointments, breakdowns by doctor and status, peak day, and a natural language summary.

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

- Node.js (v18 or later recommended)
- npm or yarn

### Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/your-username/medischeduler.git
    cd medischeduler
    ```

2.  **Install NPM packages:**
    ```sh
    npm install
    ```

3.  **Set up environment variables:**
    Create a `.env.local` file in the root of your project and add your Gemini API key.
    ```
    # .env.local
    GEMINI_API_KEY=your_gemini_api_key
    ```

4.  **Run the development server:**
    ```sh
    npm run dev
    ```

Open (https://9000-firebase-studio-1756888049128.cluster-qxqlf3vb3nbf2r42l5qfoebdry.cloudworkstations.dev/dashboard) with your browser to see the result.
