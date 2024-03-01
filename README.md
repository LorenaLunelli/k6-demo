# k6-demo

## Basic k6 script

```Javascript
import http from 'k6/http';
import { sleep } from 'k6';
export const options = {
  vus: 10,
  duration: '30s',
};
export default function () {
  http.get('http://test.k6.io');
  sleep(1);
}
```

## Run local command

```Bash
$ k6 run script.js
```

## Scenarios

k6 has different executors, depending on the needs of the test execution. They are divided into 3 categories:

### By number of iterations.

- `shared-iterations` shares iterations between VUs.
- `per-vu-iterations` has each VU run the configured iterations.

### By number of VUs.

- `constant-VUs` sends VUs at a constant number.
- `ramping-vus` ramps the number of VUs according to your configured stages.

### By iteration rate.

- `constant-arrival-rate` starts iterations at a constant rate.
- `ramping-arrival-rate` ramps the iteration rate according to your configured stages.

## Thresholds

We can set one or multiple failure/success parameters, such as, but not limited to:
- Request duration
- Error rate

## Load Test types

- __Smoke tests__ validate that your script works and that the system performs adequately under minimal load.

- __Average-load test__ assess how your system performs under expected normal conditions.

- __Stress tests__ assess how a system performs at its limits when load exceeds the expected average.

- __Soak tests__ assess the reliability and performance of your system over extended periods.

- __Spike tests__ validate the behavior and survival of your system in cases of sudden, short, and massive increases in activity.

- __Breakpoint tests__ gradually increase load to identify the capacity limits of the system.