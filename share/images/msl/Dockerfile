FROM localhost/msl_base
# .mslrc
COPY --from=MSLRC_CONTEXT ./.mslrc /tmp/msl.sh
RUN sh /tmp/msl.sh
RUN rm /tmp/msl.sh
# workspace setup
USER user
CMD /bin/bash