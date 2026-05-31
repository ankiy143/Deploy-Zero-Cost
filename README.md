# Deploy-Zero-Cost

Deploy-Zero-Cost is a zero-cost deployment automation tool designed to help you deploy applications with minimal infrastructure costs.

## Features

- 🚀 Easy deployment automation
- 💰 Zero-cost infrastructure support
- 🔄 Continuous deployment ready
- 📊 Deployment status tracking
- 🐳 Docker containerization
- ⚡ Lightweight and fast

## Prerequisites

- Python 3.8+
- Docker (optional)
- pip or conda

## Installation

### Local Setup

1. Clone the repository:
```bash
git clone https://github.com/ankiy143/Deploy-Zero-Cost.git
cd Deploy-Zero-Cost
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create `.env` file:
```bash
cp .env.example .env
```

5. Run the application:
```bash
python app.py
```

The application will be available at `http://localhost:5000`

### Docker Setup

1. Build the Docker image:
```bash
docker build -t deploy-zero-cost .
```

2. Run the container:
```bash
docker run -p 5000:5000 deploy-zero-cost
```

Or use Docker Compose:
```bash
docker-compose up
```

## API Endpoints

### Health Check
```
GET /api/health
```
Returns application health status.

### Deploy
```
POST /api/deploy
Content-Type: application/json

{
  "project": "my-project"
}
```
Initiates a deployment.

### Deployment Status
```
GET /api/status/<deployment_id>
```
Get the status of a deployment.

## Usage Example

```bash
# Check health
curl http://localhost:5000/api/health

# Initiate deployment
curl -X POST http://localhost:5000/api/deploy \
  -H "Content-Type: application/json" \
  -d '{"project": "my-project"}'

# Get deployment status
curl http://localhost:5000/api/status/deploy_001
```

## Configuration

Edit `.env` file to configure:

```env
PORT=5000
DEBUG=False
ENVIRONMENT=development
```

## Project Structure

```
Deploy-Zero-Cost/
├── app.py                 # Main application
├── config.py              # Configuration
├── requirements.txt       # Python dependencies
├── Dockerfile            # Docker configuration
├── docker-compose.yml    # Docker Compose
├── .env.example          # Environment variables example
├── .gitignore            # Git ignore rules
└── README.md             # This file
```

## Development

To run in development mode:

```bash
export FLASK_APP=app.py
export FLASK_ENV=development
flask run
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Author

**ankiy143** - [GitHub Profile](https://github.com/ankiy143)

## Support

For issues and questions, please create an issue in the [GitHub repository](https://github.com/ankiy143/Deploy-Zero-Cost/issues).
