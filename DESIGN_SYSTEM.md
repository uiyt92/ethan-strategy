# 해탈코스 디자인 시스템 (Silver & Red Edition)

## 🎨 Color Palette

### Primary Colors (Red & Silver)
| Name | HEX | Usage |
|------|-----|-------|
| **Red Accent** | `#ef4444` (Tailwind red-500) | 메인 강조, CTA 버튼, 포인트 텍스트 |
| **Red Dark** | `#991b1b` (Tailwind red-800) | 배경 그라데이션, 어두운 강조 |
| **Silver Finish** | `#e5e7eb` (gray-200) | 메인 텍스트, 테두리 |
| **Silver Dark** | `#9ca3af` (gray-400) | 보조 텍스트 |

### Silver Gradient
```css
background: linear-gradient(135deg, #ffffff 0%, #d1d5db 48%, #9ca3af 100%);
```

### Background Colors
| Name | HEX / RGBA | Tailwind Class | Usage |
|------|------------|----------------|-------|
| **Deep Space** | `#050505` | `bg-[#050505]` | 페이지 전체 배경 |
| **Black Metal** | `#171717` | `bg-neutral-900` | 카드 배경 |
| **Glass** | `rgba(255, 255, 255, 0.05)` | `.glass` | 글래스모피즘 컴포넌트 |

---

## 💎 Glassmorphism Style

### The "Exodus" Glass
```css
.glass {
    background: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
}

.glass-red {
    background: rgba(239, 68, 68, 0.05); /* Red tint */
    border: 1px solid rgba(239, 68, 68, 0.2);
    box-shadow: 0 0 20px rgba(239, 68, 68, 0.1);
}
```

---

## 🧱 Typography

### Font Family
```css
font-family: 'Noto Sans KR', sans-serif;
```

### Text Hierarchy
- **Headline**: Silver Gradient or White
- **Highlight**: Red (`text-red-500`)
- **Body**: Silver (`text-gray-300`)
- **Muted**: Dark Silver (`text-gray-500`)

---

## 🧩 Components

### Metallic CTA Button
```html
<a class="relative overflow-hidden group bg-red-600 text-white font-bold py-5 px-12 rounded-full 
          text-lg shadow-[0_0_20px_rgba(239,68,68,0.5)] hover:bg-red-500 transition-all duration-300">
    <span class="relative z-10">버튼 텍스트</span>
    <div class="absolute inset-0 bg-gradient-to-r from-red-600 to-red-400 opacity-0 group-hover:opacity-100 transition duration-300"></div>
</a>
```

### Stats Badge
```html
<div class="glass p-4 rounded-2xl flex items-center gap-4">
    <span class="w-12 h-12 rounded-full bg-gradient-to-br from-gray-100 to-gray-400 text-black flex items-center justify-center">
        <i class="fa-solid fa-icon"></i>
    </span>
</div>
```

### Carousel
```html
<div class="overflow-hidden rounded-2xl border border-gray-700/50 bg-black/50 backdrop-blur-sm">
    <!-- images -->
</div>
```

---

## ⚡ Animations

### Neon Pulse
```css
@keyframes neon-pulse {
    0%, 100% { box-shadow: 0 0 10px rgba(239, 68, 68, 0.3); }
    50% { box-shadow: 0 0 25px rgba(239, 68, 68, 0.6); }
}
```
