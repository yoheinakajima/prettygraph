# prettygraph

**prettygraph** is a Python-based web application developed by [@yoheinakajima](https://twitter.com/yoheinakajima) to demonstrate a new UI pattern for text-to-knowledge graph generation. This project is a quick hack and not intended to be a robust framework, but a simple UI idea for dynamically highlighting the text input when generating knowledge graphs.

![prettygraph image](https://github.com/yoheinakajima/prettygraph/blob/main/prettygraph.jpeg?raw=true)

## Overview

The application uses Flask for the backend, rendering templates for the front end, and LiteLLM for generating predictions which transform text inputs into JSON formatted graph data. This data is then visualized using Cytoscape.js. It's important to note that the graph regenerates on every period insertion with real-time updates in the UI, providing an interactive experience.

## Features

- **Text-to-Graph Generation:** Converts user input text into a knowledge graph.
- **Dynamic UI Updates:** Graph updates with each text input that ends with a period.
- **Color-Coded Visualization:** Nodes and edges in the graph are color-coded for better visual distinction.

## Installation

This project uses Poetry for dependency management. To set up the project:

1. Clone the repository:
   ```shell
   git clone https://github.com/yoheinakajima/prettygraph
   ```

2. Navigate to the project directory:
   ```shell
   cd prettygraph
   ```

3. Install dependencies using Poetry:
   ```shell
   poetry install
   ```

4. Run the Flask application:
   ```shell
   poetry run python main.py
   ```

## Configuring Environment Variables

To run this application, you need to set up the `OPENAI_API_KEY` environment variable. Create a file named `.env` in the root directory of your project and add the following line:

   ```text
   OPENAI_API_KEY=your_openai_api_key_here
   ```

## Usage

Once the application is running and the environment variables are set, open your web browser and navigate to `http://localhost/`. Input text into the editable text box, and watch as the knowledge graph updates with each sentence termination (period).

## Future Improvements

- **Improved Tracking:** Enhance the logic for tracking nodes and edges through their flow in the text, moving away from simple keyword matching to a more sophisticated relationship mapping.
- **Manual Graph Update:** Introduce a manual update button to generate the graph as needed, reducing computational load and API costs.
- **Loading Animation:** Add a loading animation during graph generation to improve user experience by indicating processing is underway.
- **Incremental Graph Building:** Instead of regenerating the entire graph with each input, modify the existing graph by adding new elements and deduplicating nodes similarly to [mindgraph](https://github.com/yoheinakajima/mindgraph).

## Contributing

While **prettygraph** is not intended to be maintained as a robust framework, contributions are welcome. Feel free to fork the repository and submit pull requests.

## License

This project is open-sourced under the MIT License. See the LICENSE file for more details.

## Additional Resources

For those interested in exploring more about knowledge graphs:
- [InstaGraph](https://github.com/yoheinakajima/instagraph) - Web-based tool for generating knowledge graphs. Or for a web UI, try out [instagraph.ai](https://instagraph.ai) - has knowledge graph generation but not the color coded highlights.
- [mindgraph](https://github.com/yoheinakajima/mindgraph) - For generating large knowledge graphs with deduping of nodes using an LLM as new graphs are added.

## Disclaimer

This is an experimental project and may not handle all edge cases or inputs effectively.
