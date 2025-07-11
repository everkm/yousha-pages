.PHONY: tag dist
tag:
	@if [ "$(TAG)" != "" ]; then \
		git tag -f $(TAG); \
		git push -f github $(TAG); \
	fi

DEV_THEME_DIR = /Users/dayu/Coder/everkm/daobox-site-themes/theme-youlog/__everkm/theme/youlog

ifneq (, $(shell echo $$DEBUG))
  EKMP = "/Users/dayu/Coder/everkm/everkm2/be/everkm-publish/target/debug/everkm-publish"
else
  EKMP = ./node_modules/.bin/everkm-publish
endif

work:
	$(EKMP) \
		serve \
		--work-dir ../ \
		--theme youlog

preview:
	$(EKMP) web --work-dir dist
 
dist:
	if [ -d dist ]; then \
		rm -rf dist; \
	fi
	$(EKMP) serve \
		--work-dir ../ \
		--theme youlog \
		--export

install-youlog:
	everkm-publish theme install youlog --force

update-everkm:
	pnpm install everkm-publish@latest