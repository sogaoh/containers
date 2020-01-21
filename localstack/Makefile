.PHONY:


up:
		\cp -f .env.minimum .env
		TMPDIR=/private${TMPDIR} docker-compose up -d

upb:
		\cp -f .env.minimum .env
		TMPDIR=/private${TMPDIR} docker-compose up -d --build
