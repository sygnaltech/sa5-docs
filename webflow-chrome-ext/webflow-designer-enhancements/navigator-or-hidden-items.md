# Navigator | Hidden Items

Fix the visibility indicator of items that are hidden, to distinguish between CSS display: none and settings visibility hidden.&#x20;

This is the right line.&#x20;

{% code overflow="wrap" %}
```html
<div style="flex: 0 0 auto; color: var(--colors-text-secondary);">
   <div style="display: flex; height: 12px;">
      <div style="width: 12px; height: 12px; margin-left: 4px;">
         <div class="--styled-cswzrw wf-nfffx8" style="width: 12px; height: 12px;">
            <svg data-wf-icon="HideIcon" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
               <path fill-rule="evenodd" clip-rule="evenodd" d="M10.705 11.4122L13.6464 14.3536L14.3535 13.6465L2.35353 1.64648L1.64642 2.35359L4.38807 5.09524C3.39352 5.76124 2.59317 6.69436 2.08962 7.79152C2.02885 7.92392 2.02885 8.07624 2.08962 8.20865C3.11613 10.4452 5.37595 12 7.99998 12C8.96537 12 9.88147 11.7896 10.705 11.4122ZM9.9407 10.6479L5.11149 5.81865C4.25762 6.3466 3.55885 7.10172 3.09959 8.00007C4.01046 9.78177 5.86344 11 7.99998 11C8.68305 11 9.33713 10.8755 9.9407 10.6479Z" fill="currentColor"></path>
               <path d="M13.9104 8.20856C13.5777 8.93353 13.1153 9.58688 12.553 10.1389L11.846 9.43184C12.2702 9.01685 12.6276 8.5337 12.9004 8C11.9895 6.21831 10.1366 5.00004 8.00002 5.00004C7.81171 5.00004 7.62559 5.0095 7.44213 5.02798L6.57164 4.15749C7.03124 4.05443 7.50926 4.00004 8.00002 4.00004C10.6241 4.00004 12.8839 5.55491 13.9104 7.79143C13.9712 7.92383 13.9712 8.07616 13.9104 8.20856Z" fill="currentColor"></path>
            </svg>
         </div>
      </div>
   </div>
</div>
```
{% endcode %}



Just beofre that is this;

Which we can apply strikethru to;&#x20;

{% code overflow="wrap" %}
```html
<div class="--styled-lihrRi wf-1mrza4x" style="flex: 1 1 0%;">clear-button-wrapper</div>
```
{% endcode %}

