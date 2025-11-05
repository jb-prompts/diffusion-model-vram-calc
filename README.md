# 🎬 Video Diffusion VRAM Calculator

A comprehensive, serverless tool for estimating VRAM requirements for the latest video diffusion models, including cutting-edge 2025 releases like Wan 2.2, HunyuanVideo, and Humo.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue.svg)](https://pages.github.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

## 🚀 Features

### Latest Video Diffusion Models (2025)
- **Wan 2.2 Series**: T2V-A14B, I2V-A14B, TI2V-5B, S2V-14B, Animate
- **HunyuanVideo-13B**: World's largest open-source video model with temporal tiling
- **Humo-17B**: ByteDance human-centric video generation
- **Classic Models**: AnimateDiff, Stable Video Diffusion, VideoCrafter, and more

### GPU Support
- **RTX 50-Series**: RTX 5090 (32GB), RTX 5080 (16GB), RTX 5070 Ti (16GB), RTX 5070 (12GB)
- **RTX 40-Series**: Complete lineup from RTX 4060 to RTX 4090
- **RTX 30/20-Series**: Legacy support
- **AMD Radeon**: RX 6000 and 7000 series
- **Custom VRAM**: Manual input for any GPU

### Advanced Features
- **Real-time VRAM estimation** with dynamic visualization
- **Model compatibility checker** with color-coded results
- **ComfyUI workflow templates** for all major models
- **Dark/Light theme toggle** with localStorage persistence
- **Responsive design** for desktop and mobile
- **Quantization support** (GGUF Q4/Q8 variants)
- **Memory optimization tips** (temporal tiling, FP8 precision)

## 🎯 Live Demo

Visit the live calculator: [Video Diffusion VRAM Calculator](https://vramcalc4diffusion.netlify.app/)

## 📋 Quick Start

### Option 1: GitHub Pages Deployment

1. **Fork this repository**
   ```bash
   # Click the "Fork" button on GitHub or use GitHub CLI
   gh repo fork your-username/video-diffusion-vram-calculator
   ```

2. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Save settings

3. **Access your deployment**
   - Your calculator will be available at: `https://your-username.github.io/video-diffusion-vram-calculator/`

### Option 2: Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/video-diffusion-vram-calculator.git
   cd video-diffusion-vram-calculator
   ```

2. **Serve locally**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Python 2
   python -m SimpleHTTPServer 8000
   
   # Using Node.js (if you have it installed)
   npx http-server
   
   # Or simply open the HTML file in your browser
   open video-diffusion-vram-calculator.html
   ```

3. **Access locally**
   - Open your browser to `http://localhost:8000`

### Option 3: Static Hosting

Deploy to any static hosting service:
- **Netlify**: Drag and drop the HTML file
- **Vercel**: Connect your GitHub repository
- **Cloudflare Pages**: Deploy from Git
- **Firebase Hosting**: Use Firebase CLI

## 🛠️ Technical Details

### Architecture
- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **No dependencies**: Zero external libraries or frameworks
- **Serverless**: Runs entirely in the browser
- **Responsive**: Mobile-first design with CSS Grid and Flexbox

### Browser Compatibility
- **Chrome/Edge**: 88+
- **Firefox**: 85+
- **Safari**: 14+
- **Mobile browsers**: iOS Safari 14+, Chrome Mobile 88+

### Features Implementation
- **CSS Variables**: Theme switching and maintainability
- **LocalStorage**: Theme preference persistence
- **CSS Grid/Flexbox**: Responsive layouts
- **JavaScript ES6+**: Modern syntax and features

## 📊 Supported Models

### Latest Models (2025)
| Model | Min VRAM | Recommended | Description |
|-------|----------|-------------|-------------|
| Wan 2.2 T2V-A14B | 16GB | 24GB | MoE text-to-video, 720P@24fps |
| Wan 2.2 I2V-A14B | 16GB | 24GB | Image-to-video with improved stability |
| Wan 2.2 TI2V-5B | 8GB | 24GB | Hybrid text+image-to-video |
| HunyuanVideo-13B | 8GB | 24GB | Largest open-source video model |
| Humo-17B | 24GB | 32GB | Human-centric video generation |

### Classic Models
| Model | Min VRAM | Recommended | Description |
|-------|----------|-------------|-------------|
| AnimateDiff (SD 1.5) | 8GB | 12GB | Text-to-video with motion modules |
| Stable Video Diffusion | 8GB | 16GB | Image-to-video generation |
| SVD-XT | 12GB | 20GB | Extended frame model |

## 🎨 Customization

### Modifying Models
Edit the `models` array in the JavaScript section:

```javascript
const models = [
    {
        name: "Your Custom Model",
        minVram: 8,
        recommendedVram: 16,
        description: "Your model description",
        factors: ["resolution", "frames", "batch"]
    }
    // ... more models
];
```

### Adding GPU Support
Update the GPU dropdown options:

```html
<optgroup label="Your GPU Series">
    <option value="16">Your GPU (16GB)</option>
</optgroup>
```

### Theme Customization
Modify CSS variables in the `:root` and `[data-theme="dark"]` selectors:

```css
:root {
    --accent-color: #your-color;
    --bg-gradient: your-gradient;
    /* ... other variables */
}
```

## 🔧 Advanced Configuration

### Calculation Algorithm
The VRAM estimation uses this formula:
```
Total VRAM = (Resolution × Frames × Batch × Precision) + Model Overhead + System Overhead
```

### Adding New Workflows
Add workflow cards to the workflow grid:

```html
<div class="workflow-card">
    <div class="workflow-title">🎯 Your Workflow</div>
    <div class="workflow-description">Description here</div>
    <div class="workflow-specs">
        <strong>Requirements:</strong> VRAM requirements<br>
        <strong>Models:</strong> Required models<br>
        <strong>Output:</strong> Output specifications
    </div>
</div>
```

## 📱 Mobile Optimization

The calculator is fully responsive with:
- **Adaptive layouts**: Single column on mobile devices
- **Touch-friendly controls**: Large tap targets and sliders
- **Optimized typography**: Readable text at all screen sizes
- **Theme toggle repositioning**: Mobile-friendly placement

## 🤝 Contributing

We welcome contributions! Here's how to get started:

### Bug Reports
1. Check existing issues
2. Create a detailed issue with:
   - Browser and version
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots if applicable

### Feature Requests
1. Check if the feature already exists
2. Create an issue with:
   - Clear description of the feature
   - Use case and benefits
   - Implementation suggestions

### Pull Requests
1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Test thoroughly
5. Commit with clear messages
6. Push and create a pull request

### Development Guidelines
- **Keep it simple**: No external dependencies
- **Mobile-first**: Test on mobile devices
- **Accessibility**: Use semantic HTML and proper ARIA labels
- **Performance**: Optimize for fast loading
- **Browser compatibility**: Test on major browsers

## 📈 Roadmap

### Version 2.0 (Planned)
- [ ] **More models**: Integration of latest research models
- [ ] **Performance predictions**: Estimated generation times
- [ ] **Model comparison**: Side-by-side comparisons
- [ ] **Advanced filters**: Filter models by use case
- [ ] **Export results**: PDF/PNG export of compatibility charts

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Video Diffusion VRAM Calculator  @jbprompts

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 🙏 Acknowledgments

- **Model developers**: Wan AI Team, Tencent (HunyuanVideo), ByteDance (Humo), Stability AI, Runway
- **ComfyUI community**: For workflow templates and optimization techniques
- **GPU manufacturers**: NVIDIA and AMD for hardware specifications
- **Open source community**: For quantization tools and memory optimizations


## 🌟 Star History

If you find this tool useful, please consider giving it a star! ⭐

---

**Built with ❤️ for the AI video generation community**

*Stay updated with the latest video diffusion models and GPU releases!*
