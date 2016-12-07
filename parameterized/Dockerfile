FROM scottsideleau/vistrails:latest
MAINTAINER Scott R. Sideleau <scott@sideleau.com>

# Add the VT file to the container
ADD a2.vt /opt/cis602-fa2016/a2/a2.vt

# Add the run script to the container
ADD run_workflow.py /opt/cis602-fa2016/a2/run_workflow.py

# Run the VT workflow via the script
ENTRYPOINT ["python", "-u", "/opt/cis602-fa2016/a2/run_workflow.py", \
  "/opt/cis602-fa2016/a2/a2.vt", "parameterized"]
