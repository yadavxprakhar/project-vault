# Resources for Fitness Tracking App

## 📺 Video Tutorials
- [Build a Fitness Tracker with React & TanStack Query](https://www.youtube.com/watch?v=fVJeGUnFG7M) - Web Dev Simplified: Complete tutorial (2025 edition)
- [Workout App with React Native & Expo 2026](https://www.youtube.com/watch?v=4ABN0uZYgK0) - Simon Grimm: Modern mobile implementation with TypeScript
- [Fitness Dashboard with Recharts & React](https://www.youtube.com/watch?v=Cd0gUgvWez8) - JavaScript Mastery: Data visualization and progress tracking
- [Exercise API Integration with ExerciseDB](https://www.youtube.com/watch?v=ntCzVOTkKPg) - Exercise database API tutorial with animations

## 📚 Written Tutorials
- [Build a Fitness Tracker with React & Next.js 15](https://www.freecodecamp.org/news/how-to-build-a-fitness-tracker/) - freeCodeCamp guide (updated 2026)
- [Workout Logging Database Design with Prisma](https://drawsql.app/templates/workout-tracker) - Database schema examples
- [React Native Fitness App with Expo & NativeWind](https://blog.logrocket.com/build-fitness-tracker-react-native/) - LogRocket mobile tutorial (2025 update)
- [Chart.js & Recharts for Fitness Data Visualization](https://www.chartjs.org/docs/latest/samples/line/line.html) - Line chart and progress examples

## 🔧 Tools & Libraries

### Data Visualization
- [Recharts](https://recharts.org/) - Composable charting library - **RECOMMENDED**
- [Chart.js](https://www.chartjs.org/) - Simple yet flexible charts
- [Victory](https://formidable.com/open-source/victory/) - React Native charts
- [Nivo](https://nivo.rocks/) - D3-based React charts

### Exercise Databases
- [ExerciseDB API](https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb) - 1300+ exercises with animations (free tier available)
- [WGER API](https://wger.de/en/software/api) - Open-source workout manager API
- [Nutritionix API](https://www.nutritionix.com/business/api) - Food and nutrition database

### Mobile Development
- [React Native](https://reactnative.dev/) - Cross-platform mobile framework
- [Expo](https://expo.dev/) - React Native framework with managed workflow
- [React Native Paper](https://reactnativepaper.com/) - Material Design components
- [NativeWind](https://www.nativewind.dev/) - Tailwind CSS for React Native

### Health Integrations
- [Apple HealthKit](https://developer.apple.com/documentation/healthkit) - iOS health data
- [Google Fit API](https://developers.google.com/fit) - Android health data
- [Fitbit API](https://dev.fitbit.com/) - Fitbit device integration

## 💻 GitHub Repositories
- [Fitness Tracker React](https://github.com/topics/fitness-tracker) - Various implementations
- [Workout Planner with Next.js & Prisma](https://github.com/jwenjian/ghiblog) - Full-stack example
- [React Native Fitness App](https://github.com/StephenGrider/AdvancedReactNative) - Mobile app examples
- [WGER Workout Manager](https://github.com/wger-project/wger) - Open-source fitness platform
- [Strong App Clone with React Native](https://github.com/topics/workout-tracker) - Workout logging examples

## 📖 Learning Resources

### Fitness Domain Knowledge
- [Exercise Database](https://www.bodybuilding.com/exercises/) - Exercise information
- [Progressive Overload](https://www.strongerbyscience.com/progressive-overload/) - Training principles
- [Workout Programming](https://www.reddit.com/r/Fitness/wiki/getting_started/) - Reddit fitness wiki
- [Nutrition Basics](https://www.eatright.org/food/nutrition) - Academy of Nutrition

### Data Visualization
- [Recharts Documentation](https://recharts.org/en-US/api) - Complete Recharts guide
- [Data Viz Best Practices](https://www.storytellingwithdata.com/) - Effective charts
- [Chart Selection Guide](https://www.data-to-viz.com/) - Choosing the right chart

### Mobile Development
- [React Native Tutorial](https://reactnative.dev/docs/tutorial) - Official getting started
- [Expo Documentation](https://docs.expo.dev/) - Expo guides
- [React Native Navigation](https://reactnavigation.org/) - Navigation library

## 🌐 APIs & Services
- [ExerciseDB](https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb) - Exercise database (free tier available)
- [Nutritionix API](https://www.nutritionix.com/business/api) - Food and nutrition data
- [Spoonacular API](https://spoonacular.com/food-api) - Recipe and meal planning
- [USDA FoodData Central](https://fdc.nal.usda.gov/api-guide.html) - Nutritional information
- [Edamam Nutrition API](https://developer.edamam.com/edamam-nutrition-api) - Food analysis

## 🎨 Design Resources
- [Fitness App UI Designs](https://dribbble.com/search/fitness-app) - Dribbble inspiration
- [MyFitnessPal Design](https://www.myfitnesspal.com/) - Popular fitness app reference
- [Strong App](https://www.strong.app/) - Workout logging UI inspiration
- [Figma Fitness Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=fitness+app) - Free templates

## 📚 Database Schema Example
```prisma
model User {
  id        String    @id @default(cuid())
  email     String    @unique
  name      String
  weight    Float?
  height    Float?
  age       Int?
  gender    String?
  goals     Goal[]
  workouts  Workout[]
  measurements Measurement[]
  photos    ProgressPhoto[]
  createdAt DateTime  @default(now())
}

model Exercise {
  id          String  @id @default(cuid())
  name        String
  description String?
  category    String  // strength, cardio, flexibility
  muscleGroup String  // chest, back, legs, etc.
  equipment   String? // barbell, dumbbell, bodyweight
  imageUrl    String?
  videoUrl    String?
  instructions String[]
  workoutSets WorkoutSet[]
}

model Workout {
  id          String       @id @default(cuid())
  userId      String
  user        User         @relation(fields: [userId], references: [id])
  name        String?
  date        DateTime     @default(now())
  duration    Int?         // minutes
  notes       String?
  sets        WorkoutSet[]
  completed   Boolean      @default(false)
}

model WorkoutSet {
  id         String   @id @default(cuid())
  workoutId  String
  workout    Workout  @relation(fields: [workoutId], references: [id])
  exerciseId String
  exercise   Exercise @relation(fields: [exerciseId], references: [id])
  setNumber  Int
  reps       Int?
  weight     Float?   // kg or lbs
  duration   Int?     // seconds (for timed exercises)
  distance   Float?   // km or miles (for cardio)
  restTime   Int?     // seconds
  completed  Boolean  @default(false)
}

model Measurement {
  id        String   @id @default(cuid())
  userId    String
  user      User     @relation(fields: [userId], references: [id])
  date      DateTime @default(now())
  weight    Float?
  bodyFat   Float?
  chest     Float?
  waist     Float?
  hips      Float?
  arms      Float?
  thighs    Float?
}

model Goal {
  id          String   @id @default(cuid())
  userId      String
  user        User     @relation(fields: [userId], references: [id])
  type        String   // weight, strength, endurance
  target      Float
  current     Float
  deadline    DateTime?
  achieved    Boolean  @default(false)
  createdAt   DateTime @default(now())
}

### 🚀 Workout Logging Component Example

import { useState } from 'react';
import { useForm } from 'react-hook-form';

interface WorkoutSet {
  setNumber: number;
  reps: number;
  weight: number;
  completed: boolean;
}

export function WorkoutLogger({ exercise }) {
  const [sets, setSets] = useState<WorkoutSet[]>([
    { setNumber: 1, reps: 0, weight: 0, completed: false }
  ]);

  const addSet = () => {
    setSets([...sets, {
      setNumber: sets.length + 1,
      reps: sets[sets.length - 1]?.reps || 0,
      weight: sets[sets.length - 1]?.weight || 0,
      completed: false
    }]);
  };

  const updateSet = (index: number, field: string, value: number) => {
    const updated = [...sets];
    updated[index][field] = value;
    setSets(updated);
  };

  const toggleComplete = (index: number) => {
    const updated = [...sets];
    updated[index].completed = !updated[index].completed;
    setSets(updated);
  };

  return (
    <div className="workout-logger">
      <h3>{exercise.name}</h3>
      {sets.map((set, index) => (
        <div key={index} className="set-row">
          <span>Set {set.setNumber}</span>
          <input
            type="number"
            value={set.weight}
            onChange={(e) => updateSet(index, 'weight', +e.target.value)}
            placeholder="Weight (kg)"
          />
          <input
            type="number"
            value={set.reps}
            onChange={(e) => updateSet(index, 'reps', +e.target.value)}
            placeholder="Reps"
          />
          <button onClick={() => toggleComplete(index)}>
            {set.completed ? '✓' : '○'}
          </button>
        </div>
      ))}
      <button onClick={addSet}>+ Add Set</button>
    </div>
  );
}

### 📊 Progress Chart Example

import { LineChart, Line, XAxis, YAxis, Tooltip, ResponsiveContainer } from 'recharts';

export function WeightProgressChart({ measurements }) {
  const data = measurements.map(m => ({
    date: new Date(m.date).toLocaleDateString(),
    weight: m.weight
  }));

  return (
    <ResponsiveContainer width="100%" height={300}>
      <LineChart data={data}>
        <XAxis dataKey="date" />
        <YAxis />
        <Tooltip />
        <Line type="monotone" dataKey="weight" stroke="#8884d8" strokeWidth={2} />
      </LineChart>
    </ResponsiveContainer>
  );
}

