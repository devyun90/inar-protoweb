---
name: Warm Taupe Gradient
colors:
  surface: '#fcf9f7'
  surface-dim: '#dcd9d8'
  surface-bright: '#fcf9f7'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f6f3f1'
  surface-container: '#f0edeb'
  surface-container-high: '#eae8e6'
  surface-container-highest: '#e5e2e0'
  on-surface: '#1b1c1b'
  on-surface-variant: '#4f443f'
  inverse-surface: '#30302f'
  inverse-on-surface: '#f3f0ee'
  outline: '#82746e'
  outline-variant: '#d3c3bc'
  surface-tint: '#755849'
  primary: '#5b4133'
  on-primary: '#ffffff'
  primary-container: '#755849'
  on-primary-container: '#f7d0bd'
  inverse-primary: '#e4bfac'
  secondary: '#755849'
  on-secondary: '#ffffff'
  secondary-container: '#ffd8c4'
  on-secondary-container: '#795c4d'
  tertiary: '#514532'
  on-tertiary: '#ffffff'
  tertiary-container: '#695c48'
  on-tertiary-container: '#e8d6bc'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#ffdbca'
  primary-fixed-dim: '#e4bfac'
  on-primary-fixed: '#2b170b'
  on-primary-fixed-variant: '#5b4133'
  secondary-fixed: '#ffdbc9'
  secondary-fixed-dim: '#e4bfac'
  on-secondary-fixed: '#2b170b'
  on-secondary-fixed-variant: '#5b4132'
  tertiary-fixed: '#f2e0c6'
  tertiary-fixed-dim: '#d6c4ab'
  on-tertiary-fixed: '#231a0a'
  on-tertiary-fixed-variant: '#514532'
  background: '#fcf9f7'
  on-background: '#1b1c1b'
  surface-variant: '#e5e2e0'
typography:
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.02em
  headline-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 26px
    fontWeight: '700'
    lineHeight: 32px
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 22px
    fontWeight: '700'
    lineHeight: 28px
  display-number:
    fontFamily: Plus Jakarta Sans
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 48px
  body-lg:
    fontFamily: Quicksand
    fontSize: 18px
    fontWeight: '500'
    lineHeight: 26px
  body-md:
    fontFamily: Quicksand
    fontSize: 16px
    fontWeight: '500'
    lineHeight: 24px
  label-md:
    fontFamily: Quicksand
    fontSize: 14px
    fontWeight: '700'
    lineHeight: 20px
    letterSpacing: 0.01em
  label-sm:
    fontFamily: Quicksand
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
rounded:
  sm: 0.5rem
  DEFAULT: 1rem
  md: 1.5rem
  lg: 2rem
  xl: 3rem
  full: 9999px
spacing:
  base: 8px
  margin-page: 24px
  gap-section: 40px
  gutter: 16px
  stack-sm: 4px
  stack-md: 12px
  stack-lg: 20px
---

## Brand & Style
The brand personality is nurturing, calm, and sophisticated, tailored for modern parents. The design system prioritizes a sense of safety and "soft-touch" digital experiences through organic shapes and a gentle color palette. 

The style is a hybrid of **Minimalism** and **Tactile Softness**. It avoids the clinical coldness of traditional health apps by utilizing warm gradients and deep, earthy tones. The UI should evoke an emotional response of serenity and reliability, reducing the cognitive load for tired parents through clear hierarchy and a spacious, "breathable" interface.

## Colors
The palette is rooted in the "Warm Taupe" primary tone, providing a grounded and authoritative feel. The surface color is a soft off-white to reduce eye strain during late-night usage. 

Gradients are used strategically to signify interactivity and warmth. The **Dashboard Gradient** creates an inviting container for daily logs, while the **FAB Gradient** provides necessary contrast for primary actions. Neutral tones should lean toward the warm spectrum (peaches and creams) rather than cool greys to maintain the nurturing brand narrative.

## Typography
This design system employs a dual-font strategy. **Plus Jakarta Sans** is used for headlines and numerical data (growth charts, timers) to provide a modern, clean, and optimistic structure. Its bold weights are essential for establishing a clear visual hierarchy.

**Quicksand** is used for all body text and labels. Its naturally rounded terminals complement the "hyper-rounded" shape language of the UI, ensuring that even dense information feels approachable and soft. Line heights are generous to improve legibility for users who may be multi-tasking.

## Layout & Spacing
The layout follows a strict **8px grid** to maintain mathematical harmony. Page layouts use a **24px side margin** on mobile to ensure content doesn't feel cramped. 

Vertical rhythm is defined by a **40px gap between major sections** (e.g., between the Daily Summary and the Activity Feed), creating a distinct sense of "zones" on the dashboard. For internal card layouts, use the `stack-md` (12px) for related elements and `stack-lg` (20px) for separating logical groups.

## Elevation & Depth
Depth is achieved through **Ambient Shadows** and tonal layering rather than heavy borders. The system uses two specific shadow tiers:
- **Soft Surface (Cards):** A very light, wide-spread taupe-tinted shadow (`0 4px 20px rgba(117,88,73,0.06)`) that makes cards appear to float gently above the surface.
- **Active Elevation (FAB):** A deeper, more concentrated shadow (`0 8px 30px rgba(117,88,73,0.08)`) used for primary action buttons to pull them toward the user.

Avoid using pure black shadows; always tint shadows with the primary color to maintain the warmth of the design system.

## Shapes
The shape language is **Hyper-rounded**. This is a core brand pillar. 
- **Large Cards:** Use a fixed 32px corner radius.
- **Buttons & Chips:** Must always be fully "pill-shaped" (rounded-full) to reinforce the friendly and safe aesthetic.
- **Selection Controls:** Checkboxes and radio buttons should also lean towards rounded profiles, avoiding sharp 90-degree angles at all costs.

## Components
- **Floating Action Button (FAB):** Central action point using the `fab_action` gradient. It should be a large, circular or pill-shaped element that sits above the bottom navigation.
- **Log Cards:** Use the 32px radius and the `Soft Surface` shadow. Backgrounds should be white or extremely light peach to stand out against the `dashboard_bg` gradient.
- **Active Navigation Tabs:** Indicated by the `active_tab` gradient pill behind the icon or label, providing a soft but clear selection state.
- **Inputs:** Fields should have a light taupe stroke or a subtle fill (`#F5F0EE`), with a 16px radius. Focus states use the primary color stroke.
- **Progress Bars:** Thick, pill-shaped tracks with the primary color or a secondary gradient to visualize feeding or sleep durations.
- **Chips/Tags:** Small pill-shaped elements used for categorization (e.g., "Nap", "Feeding"), utilizing the `active_tab` gradient for selected states.
