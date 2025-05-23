# 🚀 DhanSaarthi - Mutual Fund Watchlist & Performance Analytics

A comprehensive Flutter application built for the **Flutter Developer Assessment Task**, showcasing advanced mutual fund investment tracking, performance analytics, and watchlist management capabilities.

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![GetX](https://img.shields.io/badge/GetX-9C27B0?style=for-the-badge&logo=flutter&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)

## 📋 Assessment Task Completion

### ✅ Core Requirements Implemented

#### 🔐 User Authentication (Supabase)
- **Login/Signup Screen** - Complete authentication flow with Supabase
- **Session Management** - Secure token storage with persistent login state
- **Navigation Flow** - Automatic redirect to dashboard on successful authentication
- **Error Handling** - Comprehensive error management for auth failures

#### 📊 Dashboard Implementation
- **Fund Performance Section** - Detailed view of selected mutual funds
- **My Watchlist Section** - Complete watchlist management system
- **Real-time Updates** - Live data synchronization across components
- **Responsive Design** - Optimized for various screen sizes

#### 📈 Mutual Fund Performance Analytics (Charts)
- **Interactive Line Charts** - NAV trend visualization using FL Chart
- **Multiple Date Ranges** - 1M, 3M, 6M, 1Y, 3Y, MAX options
- **Complex Chart Features**:
  - Dual-line comparison (Fund vs Benchmark)
  - Interactive tooltips with precise data points
  - Smooth animations and transitions
  - Performance metrics overlay
  - Investment calculator integration

#### 🗂️ Watchlist Management
- **Multiple Watchlists** - Create unlimited watchlists with unique names
- **Fund-Only Support** - Exclusive mutual fund tracking (no stocks)
- **Local Persistence** - Data stored using GetStorage (SharedPreferences alternative)
- **CRUD Operations** - Add, remove, rename, delete watchlists
- **Interactive UI** - Swipe to delete, tap to select, long-press for options

#### 🎯 State Management & Navigation
- **GetX Framework** - Reactive state management with dependency injection
- **Clean Architecture** - Modular controller-based structure
- **Smooth Transitions** - Optimized navigation with loading states
- **Memory Management** - Proper disposal and lifecycle management

### 🌟 Bonus Features Implemented

#### 🔍 Advanced Sorting & Filtering
- **Multiple Sort Options**:
  - Sort by NAV (High to Low / Low to High)
  - Sort by 1Y Returns (Best to Worst / Worst to Best)
  - Sort by 3Y Returns (Best to Worst / Worst to Best)
  - Sort by 5Y Returns (Best to Worst / Worst to Best)
  - Sort by Expense Ratio (Low to High / High to Low)
  - Alphabetical sorting (A-Z / Z-A)

#### 🔥 Heatmap Feature
- **Performance Heatmap** - Visual representation of fund performance
- **Color-coded Returns** - Green for positive, red for negative returns
- **Interactive Grid** - Tap to view detailed fund information
- **Time Period Selection** - Switch between different return periods

## 📱 App Screenshots

| Authentication Flow | Dashboard | Charts Analytics | Watchlist Management |
|:---:|:---:|:---:|:---:|
| ![Auth](https://via.placeholder.com/200x400/000000/FFFFFF?text=Auth+Flow) | ![Dashboard](https://via.placeholder.com/200x400/000000/FFFFFF?text=Dashboard) | ![Charts](https://via.placeholder.com/200x400/000000/FFFFFF?text=Charts) | ![Watchlist](https://via.placeholder.com/200x400/000000/FFFFFF?text=Watchlist) |

## 🏗️ Technical Architecture

### **State Management Pattern**
```dart
// GetX Reactive Programming
class DashboardController extends GetxController {
  final RxList<MutualFund> funds = <MutualFund>[].obs;
  final Rx<MutualFund?> selectedFund = Rx<MutualFund?>(null);
  
  // Reactive UI updates automatically when data changes
  void selectFund(MutualFund fund) {
    selectedFund.value = fund;
  }
}

