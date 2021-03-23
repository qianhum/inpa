# 📦 Is New Package Available

A web service periodically checks if your favorite NPM packages get new update.

[API Spec](api-spec/README.md)

## Backend

[Written with TypeScript, Express.js and Node.js](https://github.com/qianhum/inpa-web-backend)

## Frontend

[Written with TypeScript, Next.js and React.js](https://github.com/qianhum/inpa-web-frontend)

## Usage

Backend and frontend do not have to run on same machine.

- Backend

```bash
docker run -dp 20000:20000 qianhum/inpa-web-backend
```

- Frontend

```bash
docker run -dp 80:80 qianhum/inpa-web-frontend
```

## License

AGPL 3.0 or later
