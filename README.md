# unit2-assignment

Certainly! Here’s a sample documentation for your GitHub `README.md` file that outlines your WebGL assignment, including details on the project, how to run it, and an overview of the code:

```markdown
# WebGL Polygon Example

## Overview

This project demonstrates the use of WebGL to render a 5-vertex polygon with a spinning animation. The polygon is colored either red or blue, and it rotates slowly around its axes. The assignment showcases basic WebGL functionality, including creating shaders, setting up buffers, and applying transformations.

## Features

- **5-Vertex Polygon**: Creates a polygon composed of five vertices.
- **Color**: The polygon is rendered with a red surface.
- **Rotation**: The polygon spins slowly around its X and Y axes.
- **Documentation**: The JavaScript code is well-commented to explain each part of the implementation.

## Technologies Used

- **WebGL**: For rendering 3D graphics in the browser.
- **HTML5**: To create the web page and canvas element.
- **JavaScript**: For writing the WebGL code and handling animations.

## Getting Started

### Prerequisites

- A modern web browser with WebGL support.

### Running the Example

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/webgl-polygon-example.git
   cd webgl-polygon-example
   ```

2. **Open the HTML File**:
   Open `index.html` in a web browser. You should see a 5-vertex polygon spinning on the canvas.

## Code Explanation

### Vertex and Fragment Shaders

- **Vertex Shader**: Defines the position of each vertex in 3D space and applies the model-view-projection transformation.
- **Fragment Shader**: Sets the color of the polygon's surface.

### JavaScript Code

- **Setup WebGL**: Initializes the WebGL context and checks for support.
- **Create Shaders**: Compiles and links the vertex and fragment shaders.
- **Define Vertices**: Specifies the coordinates for the 5-vertex polygon.
- **Draw Function**: Clears the canvas, sets up the shader program, applies the color, and draws the polygon with rotation.

### Example Code

Here’s a brief snippet from the code illustrating the setup and rendering process:

```javascript
const canvas = document.getElementById('webgl-canvas');
const gl = canvas.getContext('webgl');

// Vertex Shader Source
const vertexShaderSource = `
    attribute vec3 a_position;
    uniform mat4 u_modelViewProjection;
    void main() {
        gl_Position = u_modelViewProjection * vec4(a_position, 1.0);
    }
`;

// Fragment Shader Source
const fragmentShaderSource = `
    precision mediump float;
    uniform vec4 u_color;
    void main() {
        gl_FragColor = u_color;
    }
`;

// Create and Compile Shaders
function createShader(gl, sourceCode, type) {
    const shader = gl.createShader(type);
    gl.shaderSource(shader, sourceCode);
    gl.compileShader(shader);
    if (!gl.getShaderParameter(shader, gl.COMPILE_STATUS)) {
        console.error('Shader compile error:', gl.getShaderInfoLog(shader));
        gl.deleteShader(shader);
        return null;
    }
    return shader;
}
```

## Contributing

Feel free to open issues or submit pull requests if you have suggestions for improvements or fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- WebGL Documentation: [WebGL Specification](https://www.khronos.org/registry/webgl/specs/latest/)

For further details, refer to the comments in the source code or reach out with questions.

```
