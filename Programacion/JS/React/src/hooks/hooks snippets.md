## Http request

```js
import { useState, useCallback } from "react";

const useHttp = () => {

    const [isLoading, setIsLoading] = useState(false);
    const [error, setError] = useState(null);

    const sendRequest = useCallback(async (requestConfig,applyData) => {
        setIsLoading(true);
        setError(null);
        try {
            const response = await fetch(
                requestConfig.url,
                {
                    method: requestConfig.method ? requestConfig.method : 'GET',
                    headers: requestConfig.headers ? requestConfig.headers : {},
                    body: requestConfig.body ? JSON.stringify(requestConfig.body) : null
                }
            );

            if (!response.ok) {
                throw new Error('Request failed!');
            }
            const data = await response.json();
            applyData(data);
        } catch (err) {
            setError(err.message || 'Something went wrong!');
        }
        setIsLoading(false);
    },[]);

    return {
        isLoading, error, sendRequest
    }
};

export default useHttp;

```

Para usarlo 

```js
const [tasks, setTasks] = useState([]);
const {isLoading, error, sendRequest: fetchTasks} = useHttp();

 useEffect(() => {
    const transformationTasks = tasksObj => {
      const loadedTasks = [];
      for (const taskKey in tasksObj) {
        loadedTasks.push({ id: taskKey, text: tasksObj[taskKey].text });
      }
      setTasks(loadedTasks);
    };

	const reqObject = {url: 'https://react-http-c7074-default-rtdb.firebaseio.com/tasks.json'};

    fetchTasks( reqObject, transformationTasks);
  }, [fetchTasks]);
```